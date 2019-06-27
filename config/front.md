#### class

`class` 是作为图形形状的重要过滤条件

**示例**

`class="winning-chart winning-bar"`

**注意：winning-chart固定值，winning-bar代表需要的图形**

**属性说明**

属性名|说明
:-:|:-:
winning-bar|柱形图
winning-line|折线图
winning-card|卡片图
winning-ringc|环形图

---

#### data-config

`data-config` 作为请求地址和请求配置的重要参数,内部属于一个json对象
- 类型：Object

**属性说明**

|属性名|说明|类型|默认值|
|:-|:-|:-|:-:|
|url|请求后台接口url地址|String|-|
|data|附带的额外参数|Object|-|

**示例**

```html
 data-config="{
 	url: 'chart.do?getBar',
 	data:{
 		id:'3'
 	}
 }"
```