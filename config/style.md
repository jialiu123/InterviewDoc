## TextStyle
>TextStyle文字Style设置，一般title会用到

**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|color|颜色|String|-|
|align|对齐方式|枚举X<br/>center, left, right|-|
|decoration|修饰，仅对tooltip.textStyle生效|String|-|
|fontSize|字号 ，单位px|Integer|-|
|fontFamily|字体系列|String|-|
|fontFamily2|字体系列 IE8- 字体模糊并且，不支持不同字体混排，额外指定一份|String|-|
|fontStyle| 样式|枚举FontStyle<br/>normal, italic, oblique|-|
|fontWeight|字号粗细,同CSS|Object|-|
|backgroundColor|背景色|String|-|
|borderRadius|文字块的圆角|Object|-|
|padding|边距|Object|-|

## LineStyle
>LineStyle线Style设置，折线图一般会用到

**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|opacity|图形透明度。支持从 0 到 1 的数字，为 0 时不绘制该图形|Double|-|
|color|阳线颜色|Object|-|
|color0|阴线颜色|Object|-|
|type|线条样式|枚举LineType<br/>solid, dotted, dashed, broken, curve|-|
|width|线宽|Integer|-|
|shadowColor|折线主线(IE8+)有效，阴影色彩，支持rgba|String|-|
|shadowBlur|默认值5，折线主线(IE8+)有效，阴影模糊度，大于0有效|Integer|-|
|shadowOffsetX|默认值3，折线主线(IE8+)有效，阴影横向偏移，正值往右，负值往左|Integer|-|
|shadowOffsetY|默认值3，折线主线(IE8+)有效，阴影纵向偏移，正值往下，负值往上|Integer|-|
|normal|normal属性|Normal|-|
|emphasis|emphasis属性|Emphasis|-|

## ItemStyle
>ItemStyle图标每个元素Style设置，比如柱形图每个柱子的设置

**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|color|阳线颜色|Object|-|
|color0|阴线颜色|Object|-|
|normal|默认样式|Normal|-|
|emphasis|强调样式（悬浮时样式）|Emphasis|-|
|breadcrumb|面包屑|Breadcrumb|-|
|childBorderWidth|二级边框宽度|Integer|-|
|childBorderColor|二级边框颜色|Object|-|

## AreaStyle
>AreaStyle面积Style设置，一般面积图会用到

**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|color|颜色|Object|-|
|type|填充样式，目前仅支持'default'(实填充)|Object|-|
