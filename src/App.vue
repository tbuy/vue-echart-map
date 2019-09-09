<template>
    <div id="app">
        <EchartMap :mapData="mapData" style="width: 100%;height: 100vh" :mapOption="{
            'title': '地图title',
            'titleColor': 'pink'
        }"></EchartMap>
    </div>
</template>
<script>
    import EchartMap from './components/EchartMap'
    export default {
        components: {
            EchartMap
        },
        data() {
            return {
                mapData: [{
                        "flight_ids": "11,18,24",
                        "from": "保山",
                        "from_longitude": "99.1729",
                        "from_latitude": "25.05753",
                        "to": "南昌",
                        "to_longitude": "115.9000015258789",
                        "to_latitude": "28.864999771118164",
                        "num": 483
                    },
                    {
                        "flight_ids": "32,41,53,60,68,77,81",
                        "from": "烟台",
                        "from_longitude": "121.37200164794922",
                        "from_latitude": "37.40169906616211",
                        "to": "沈阳",
                        "to_longitude": "123.48300170898438",
                        "to_latitude": "41.639801025390625",
                        "num": 237
                    },
                    {
                        "flight_ids": "33,40,48,52,61,69,76,80",
                        "from": "昆明",
                        "from_longitude": "102.9291667",
                        "from_latitude": "25.1019444",
                        "to": "烟台",
                        "to_longitude": "121.37200164794922",
                        "to_latitude": "37.40169906616211",
                        "num": 395
                    },
                    {
                        "flight_ids": "34,50,54,62,70,78,82,90,98",
                        "from": "沈阳",
                        "from_longitude": "123.48300170898438",
                        "from_latitude": "41.639801025390625",
                        "to": "烟台",
                        "to_longitude": "121.37200164794922",
                        "to_latitude": "37.40169906616211",
                        "num": 717
                    },
                    {
                        "flight_ids": "35,43,55,63,71,79,83,91",
                        "from": "烟台",
                        "from_longitude": "121.37200164794922",
                        "from_latitude": "37.40169906616211",
                        "to": "昆明",
                        "to_longitude": "102.9291667",
                        "to_latitude": "25.1019444",
                        "num": 1125
                    },
                    {
                        "flight_ids": "36,44,59,64,72,87",
                        "from": "无锡",
                        "from_longitude": "120.429000854",
                        "from_latitude": "31.494400024399997",
                        "to": "丽江",
                        "to_longitude": "100.246002197",
                        "to_latitude": "26.6800003052",
                        "num": 733
                    },
                    {
                        "flight_ids": "37,57,67,74,85",
                        "from": "无锡",
                        "from_longitude": "120.429000854",
                        "from_latitude": "31.494400024399997",
                        "to": "昆明",
                        "to_longitude": "102.9291667",
                        "to_latitude": "25.1019444",
                        "num": 312
                    },
                    {
                        "flight_ids": "38,47,58,65,100",
                        "from": "昆明",
                        "from_longitude": "102.9291667",
                        "from_latitude": "25.1019444",
                        "to": "无锡",
                        "to_longitude": "120.429000854",
                        "to_latitude": "31.494400024399997",
                        "num": 603
                    },
                    {
                        "flight_ids": "39,45,56,66,73,86",
                        "from": "丽江",
                        "from_longitude": "100.246002197",
                        "from_latitude": "26.6800003052",
                        "to": "无锡",
                        "to_longitude": "120.429000854",
                        "to_latitude": "31.494400024399997",
                        "num": 589
                    },
                    {
                        "flight_ids": "4,10,16,22",
                        "from": "兰州",
                        "from_longitude": "103.620002747",
                        "from_latitude": "36.5152015686",
                        "to": "南昌",
                        "to_longitude": "115.9000015258789",
                        "to_latitude": "28.864999771118164",
                        "num": 398
                    },
                    {
                        "flight_ids": "5,17,23",
                        "from": "珠海",
                        "from_longitude": "113.375999",
                        "from_latitude": "22.006399",
                        "to": "南昌",
                        "to_longitude": "115.9000015258789",
                        "to_latitude": "28.864999771118164",
                        "num": 75
                    },
                    {
                        "flight_ids": "7,12,25",
                        "from": "南昌",
                        "from_longitude": "115.9000015258789",
                        "from_latitude": "28.864999771118164",
                        "to": "保山",
                        "to_longitude": "99.1729",
                        "to_latitude": "25.05753",
                        "num": 408
                    },
                    {
                        "flight_ids": "8,13,20,26",
                        "from": "南昌",
                        "from_longitude": "115.9000015258789",
                        "from_latitude": "28.864999771118164",
                        "to": "兰州",
                        "to_longitude": "103.620002747",
                        "to_latitude": "36.5152015686",
                        "num": 162
                    },
                    {
                        "flight_ids": "9,14,21,27",
                        "from": "南昌",
                        "from_longitude": "115.9000015258789",
                        "from_latitude": "28.864999771118164",
                        "to": "珠海",
                        "to_longitude": "113.375999",
                        "to_latitude": "22.006399",
                        "num": 124
                    },
                    {
                        "flight_ids": 28,
                        "from": "昆明",
                        "from_longitude": "102.9291667",
                        "from_latitude": "25.1019444",
                        "to": "成都",
                        "to_longitude": "103.9469985961914",
                        "to_latitude": "30.578500747680664",
                        "num": 10
                    },
                    {
                        "flight_ids": 29,
                        "from": "南京",
                        "from_longitude": "118.86199951171875",
                        "from_latitude": "31.742000579833984",
                        "to": "昆明",
                        "to_longitude": "102.9291667",
                        "to_latitude": "25.1019444",
                        "num": 40
                    },
                    {
                        "flight_ids": 31,
                        "from": "保山",
                        "from_longitude": "99.1729",
                        "from_latitude": "25.05753",
                        "to": "南京",
                        "to_longitude": "118.86199951171875",
                        "to_latitude": "31.742000579833984",
                        "num": 123
                    },
                    {
                        "flight_ids": 92,
                        "from": "南京",
                        "from_longitude": "118.86199951171875",
                        "from_latitude": "31.742000579833984",
                        "to": "保山",
                        "to_longitude": "99.1729",
                        "to_latitude": "25.05753",
                        "num": 13
                    },
                    {
                        "flight_ids": 93,
                        "from": "南京",
                        "from_longitude": "118.86199951171875",
                        "from_latitude": "31.742000579833984",
                        "to": "呼和浩特",
                        "to_longitude": "111.823997498",
                        "to_latitude": "40.851398468",
                        "num": 208
                    },
                    {
                        "flight_ids": 95,
                        "from": "呼和浩特",
                        "from_longitude": "111.823997498",
                        "from_latitude": "40.851398468",
                        "to": "南京",
                        "to_longitude": "118.86199951171875",
                        "to_latitude": "31.742000579833984",
                        "num": 283
                    }
                ]
            }
        }
    }

</script>
<style>
    * {
        margin: 0;
        padding: 0;
    }

</style>
