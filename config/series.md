**说明：series系列主要封装每个图形的属性，比如柱状图柱子的宽度，颜色等属性**

## Series
>基础series对于公共属性的封装，是series系列的父类

**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|legendHoverLink|是否启用图例（legend）hover时的联动响应（高亮显示）|Boolean|-|
|xAxisIndex|xAxis坐标轴数组的索引，指定该系列数据所用的横坐标轴|Integer|-|
|yAxisIndex|yAxis坐标轴数组的索引，指定该系列数据所用的纵坐标轴|Integer|-|
|geoIndex|使用的地理坐标系的 index，在单个图表实例中存在多个地理坐标系的时候有用|Integer|-|
|name|系列名称，如启用legend，该值将被legend.data索引相关|String|-|
|type|图表类型，必要参数！如为空或不支持类型，则该系列数据不被显示|SeriesType 枚举类型|-|
|stack|组合名称，多组数据的堆积图时使用，eg：stack:'group1'，则series数组中stack值等于'group1'的数据做堆积计算|String|-|
|symbol|标志图形类型，默认自动选择（8种类型循环使用，不显示标志图形可设为'none'）|String|-|
|symbolSize|标志图形大小，可计算特性启用情况建议增大以提高交互体验。实现气泡图时symbolSize需为Function，气泡大小取决于该方法返回值，传入参数为当前数据项（value数组）|String|-|
|symbolRoate|标志图形旋转角度[-180,180]|String|-|
|symbolOffset|标记相对于原本位置的偏移|String[]|-|
|showAllSymbol|标志图形默认只有主轴显示（随主轴标签间隔隐藏策略），如需全部显示可把showAllSymbol设为true|Boolean|-|
|calculable|重新计算|Boolean|-|
|zlevel|一级层叠控制|Integer|-|
|markPoint|标注|MarkPoint|-|
|markLine|标线|MarkLine|-|
|label|图形上的文本标签，课用于说明图形的一些数据信息，比如值，名称等|[ItemStyle](config/style.md?id=ItemStyle)|-|
|coordinateSystem|坐标系|String|-|

## BarSeries
**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|barMinHeight|柱条最小高度，可用于防止某item的值过小而影响交互|Integer|-|
|barMaxWidth|柱条（K线蜡烛）宽度，不设时自适应|Integer|50|
|barGap|柱间距离，默认为柱形宽度的30%，可设固定值|String|-|
|barCategoryGap|类目间柱形距离，默认为类目间距的20%，可设固定值|String|-|

## LineSeries
**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|smooth|平滑曲线|Boolean|-|
|areaStyle|区域填充样式|[AreaStyle](config/style.md?id=AreaStyle)|-|
|lineStyle|折线样式|[LineStyle](config/style.md?id=LineStyle)|-|


## CardSeries
暂无

## RingcSeries
暂无