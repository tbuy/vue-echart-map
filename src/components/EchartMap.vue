<template>
    <div id="mapChart" class="chart"></div>
</template>
<script>
    import echarts from "echarts";
    import axios from 'axios'
    export default {
        props: {
            mapData: {
                type: Array,
                default: [],
            },
            mapOption: {
                type: Object,
            }

        },
        computed: {
            // 通过计算值，将mapOption的默认值补全
            chartOption() {
                return {
                    'title': '地图',
                    'titleColor': '#8796B0',
                    'backgroundColor': '#2B3648',
                    'areaColor': '#262C38',
                    'borderColor': '#678EE3',
                    'hoverAreaColor': '#16467B',
                    'lineColor': 'rgb(192, 158, 255)',
                    'trailColor': '#fff',
                    'endColor': 'rgb(192, 158, 255)',
                    ...this.mapOption
                }
            }
        },
        methods: {
            mapChart() {
                var myChart = echarts.init(document.getElementById('mapChart'));

                axios.get("./static/json/map/100000.json", {}).then(response => {
                    var chinaJson = response.data;
                    echarts.registerMap("china", chinaJson);
                    var series = [];
                    series.push({
                        type: 'lines',
                        zlevel: 1,
                        effect: {
                            show: true,
                            period: 6,
                            trailLength: 0.7,
                            color: this.chartOption.trailColor,
                            symbolSize: 3
                        },
                        lineStyle: {
                            normal: {
                                width: 0,
                                curveness: 0.2
                            }
                        },
                        data: this.initData1(this.mapData)
                    }, {
                        type: 'lines',
                        zlevel: 2,
                        effect: {
                            show: true,
                            period: 6,
                            trailLength: 0,
                            symbolSize: 5
                        },
                        lineStyle: {
                            normal: {
                                color: this.chartOption.lineColor,
                                width: 1,
                                opacity: 0.4,
                                curveness: 0.2
                            }
                        },
                        data: this.initData1(this.mapData)
                    }, {
                        type: 'effectScatter',
                        coordinateSystem: 'geo',
                        zlevel: 2,
                        rippleEffect: {
                            brushType: 'stroke'
                        },
                        label: {
                            normal: {
                                show: true,
                                position: 'right',
                                formatter: '{b}'
                            }
                        },
                        symbolSize: function (val) {
                            return val[2] / 8;
                        },
                        data: this.initData2(this.mapData)
                    }, {
                        type: 'effectScatter',
                        coordinateSystem: 'geo',
                        zlevel: 2,
                        rippleEffect: {
                            brushType: 'stroke'
                        },
                        label: {
                            normal: {
                                show: true,
                                position: 'right',
                                formatter: '{b}'
                            }
                        },
                        symbolSize: function (val) {
                            return val[2] / 8;
                        },
                        itemStyle: {
                            normal: {
                                color: this.chartOption.endColor
                            }
                        },
                        data: this.initData2(this.mapData)
                    });

                    myChart.setOption({
                        backgroundColor: this.chartOption.backgroundColor,
                        title: {
                            text: this.chartOption.title,
                            left: 20,
                            top: 10,
                            textStyle: {
                                fontSize: 16,
                                fontFamily: 'PingFangSC-Regular',
                                fontWeight: 'lighter',
                                color: this.chartOption.titleColor
                            }
                        },
                        tooltip: {
                            trigger: 'item',
                            formatter: (param) => {
                                var data = param.data;
                                return data.fromName + ' - ' + data.toName + ' : ' + data.value;
                            }
                        },
                        legend: {
                            orient: 'vertical',
                            top: 'bottom',
                            left: 'right',
                            selectedMode: 'single'
                        },
                        geo: {
                            map: 'china',
                            label: {
                                emphasis: {
                                    show: false
                                }
                            },
                            roam: true,
                            itemStyle: {
                                normal: {
                                    areaColor: this.chartOption.areaColor,
                                    borderColor: this.chartOption.borderColor
                                },
                                emphasis: {
                                    areaColor: this.chartOption.hoverAreaColor
                                }
                            }
                        },
                        series: series
                    });

                });
            },
            initData1(data) {
                var reault = [];
                for (var i = 0; i < data.length; i++) {
                    var el = data[i];
                    var fromData = `${el.from_longitude},${el.from_latitude}`.split(',')
                    var toData = `${el.to_longitude},${el.to_latitude}`.split(',')
                    var val = []
                    val.push(fromData, toData)
                    reault.push({
                        fromName: el.from,
                        toName: el.to,
                        coords: val,
                        value: el.num
                    })
                }
                return reault;
            },
            initData2(data) {
                var reault = [];
                for (var i = 0; i < data.length; i++) {
                    var el = data[i];
                    var val = `${el.to_longitude},${el.to_latitude},30`.split(',')
                    reault.push({
                        name: el.to,
                        value: val
                    })
                }
                return reault;
            },
        },
        mounted() {
            this.mapChart();
        },
    }

</script>
<style scoped>


</style>
