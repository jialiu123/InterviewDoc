**说明：options主要封装全局设置，比如说图表的标题，提示框、工具箱属性**

## Option
>基础Option主要封装了所有的属性，最终对外数据就是option

**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|title|请求后台接口url地址|[Title](config/options.md?id=Title)|-|
|legend|请求后台接口url地址|[Legend](config/options.md?id=Legend)|-|
|toolbox|请求后台接口url地址|[Toolbox](config/options.md?id=Toolbox)|-|
|tooltip|请求后台接口url地址|[Tooltip](config/options.md?id=Tooltip)|-|
|series|请求后台接口url地址|List<[Series](config/series.md)>|-|
|xAxis|请求后台接口url地址|List<[Axis](config/options.md?id=Axis)>|-|
|yAxis|请求后台接口url地址|List<[Axis](config/options.md?id=Axis)>|-|
|calculable|请求后台接口url地址|Boolean|-|

## Title
>标题相关属性设置

**示例**

```java
option.title().text("某地区蒸发量和降水量").subtext("纯属虚构");
```

**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|text|主标题文本，'\n'指定换行|String|-|
|link|主标题文本超链接|String|-|
|target|指定窗口打开主标题超链接，支持'self'、'blank'，不指定等同为'blank'（新窗口）|String|-|
|subtext|副标题文本，'\n'指定换行|String|-|
|sublink|副标题文本超链接|String|-|
|subtarget|指定窗口打开副标题超链接，支持'self'、'blank'，不指定等同为'blank'（新窗口）|String|-|
|textStyle|主标题文本样式（详见textStyle）|[TextStyle](config/style.md?id=TextStyle)|-|
|subtextStyle|默认值{color: '#aaa'}，副标题文本样式|TextStyle|-|
|offsetCenter|属性offsetCenter用于详情定位，数组为横纵相对仪表盘圆心坐标偏移，支持百分比（相对外半径）|Object|-|



## Legend
>图例组件相关设置

**示例**

```java
List<String> legendNameData = new ArrayList<String>();
legendNameData.add("蒸发量");
ChartModel chartData = new ChartModel();
chartData.legendName(legendNameData);
```

**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|orient|布局方式，默认为水平布局，可选为：'horizontal'、'vertical'|Orient|-|
|type|设置分页方式|LegendType<br/>枚举类型|-|
|itemWidth|图例图形宽度|Integer|-|
|itemHeight|图例图形高度|Integer|-|
|textStyle|文字样式|TextStyle|-|
|selectedMode|选择模式，默认开启图例开关|Object|-|
|data|配置默认选中状态，可配合LEGEND.SELECTED事件做动态数据载入|Map<String, Boolean>|-|
|data|图例内容数组，数组项通常为{string}，每一项代表一个系列的name|List|-|

## Toolbox
>工具箱相关属性设置

**示例**

```java
option.toolbox().feature(Tool.dataView, new MagicType().show(true), Tool.restore, Tool.saveAsImage);
```

**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|feature|启用功能，目前支持feature见下，工具箱自定义功能回调处理|Map<String, Feature>|-|
|orient|布局方式，默认为水平布局，可选为：'horizontal'、'vertical'|Orient|-|
|color|工具箱背景颜色，默认透明|List|-|
|disableColor|无效颜色|String|-|
|effectiveColor|激活颜色|String|-|
|itemSize|工具箱icon大小，单位（px）|Integer|-|
|showTitle|是否显示工具箱文字提示，默认启用|Boolean|-|
|iconStyle|公用的 icon 样式设置|[ItemStyle](config/style.md?id=ItemStyle)|-|



## Tooltip
>提示框相关属性设置

**示例**

```java
//默认地城已经设置好了，不需要手动设置
option.tooltip();
```

**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|showContent|tooltip主体内容显示策略|Boolean|-|
|trigger|触发类型，默认数据触发，见下图，可选为：'item'、'axis'|Trigger<br/>枚举类型|axis|
|triggerOn|提示框触发的条件|TriggerOn<br/>枚举类型||
|position|提示框浮层的位置，默认不设置时位置会跟随鼠标的位置|Object|-|
|formatter|位置指定，传入{Array}，如[x, y]， 固定位置[x, y]；传入{Function}，如function([x, y]) {return [newX,newY]}，默认显示坐标为输入参数，用户指定的新坐标为输出返回。|Object|-|
|islandFormatter|内容格式器：{string}（Template）、{Function}，支持异步回调见表格下方|String|-|
|showDelay|默认20，显示延迟，添加显示延迟可以避免频繁切换，特别是在详情内容需要异步获取的场景，单位ms|Integer|-|
|hideDelay|默认100，隐藏延迟，单位ms|Integer|-|
|transitionDuration|动画变换时长，单位s，如果你希望tooltip的跟随实时响应，showDelay设置为0是关键，同时transitionDuration设0也会有交互体验上的差别|Double|-|
|enterable|默认true，鼠标是否可进入详情气泡中，默认为false，如需详情内交互，如添加链接，按钮，可设置为true。|Boolean|-|
|borderRadius|提示边框圆角，单位px，默认为4|Integer|-|
|textStyle|文本样式，默认为白色字体|TextStyle|-|
|alwaysShowContent|是否永远显示提示框内容，默认情况下在移出可触发提示框区域后 一定时间 后隐藏，设置为 true 可以保证一直显示提示框内容|Boolean|-|
|axisPointer|坐标轴指示器，坐标轴触发有效|AxisPointer|-|

