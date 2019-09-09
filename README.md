# vue-echart-map

在vue中集成echartMap中国地图，展示飞行航线

# Demo

The demo page is [HERE](https://tbuy.github.io/vue-echart-map/dist/).

# API


名称 | 类型 | 默认值 | 是否必填 | 描述
---|--- |--- |--- | ---
mapData | Array | [] | 是 | 传入的数据
mapOption | Object | 无 | 否 | 传入的配置


### mapData

现阶段key需要按照以下命名，其他随意（待升级）

[{
    "from": "保山",
    "from_longitude": "99.1729",
    "from_latitude": "25.05753",
    "to": "南昌",
    "to_longitude": "115.9000015258789",
    "to_latitude": "28.864999771118164",
    "num": 483
}]

### mapOption

配置项暂时支持以下几项

- title
- titleColor
- backgroundColor
- areaColor
- borderColor
- hoverAreaColor
- lineColor
- trailColor
- endColor
