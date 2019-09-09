# vue-echart-map

在vue中集成echartMap中国地图，展示飞行航线

# Demo

The demo page is [HERE](https://tbuy.github.io/vue-echart-map/dist/).

![demo](./static/1.png)

# API


名称 | 类型 | 默认值 | 是否必填 | 描述
---|--- |--- |--- | ---
mapData | Array | [] | 是 | 传入的数据
mapOption | Object | 无 | 否 | 传入的配置


### mapData

现阶段以下key值是必须有的字段，其他随意（待升级）

- from 出发地
- from_longitude 出发地经度
- from_latitude 出发地纬度
- to 目的地
- to_longitude 目的地经度
- to_latitude 目的地纬度
- num 数值


### mapOption

配置项暂时支持以下几项（待升级）

- title 标题
- titleColor 标题颜色
- backgroundColor 背景色
- areaColor 地图颜色
- borderColor 地图线框颜色
- hoverAreaColor 地图高亮颜色
- lineColor 航线颜色
- trailColor 轨迹颜色
- endColor 目的地颜色
