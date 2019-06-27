## 前台安装
### JS和CSS安装
前台html需要引入我们定义好的`css文件和js文件`，需要手动下载然后使用

注意本项目依赖echarts3.0版本，所以引入的时候注意冲突

```html
<!-- import stylesheet -->
<link rel="stylesheet" href="winning-visualize-charts.css">
<!-- import echarts.js -->
<script src="echarts.min.js"></script>
<!-- import winning-visualize-charts.js -->
<script src="winning-visualize-charts.js"></script>
```

### CSS和JS下载

<a href="../static/download/winningCharts.rar">立即下载资源文件</a>

### 完整示例
**注意html中**：`<div class="winning-chart winning-bar" data-config="{url: 'chart.do?getBar'}"></div>`<br/>
**class说明**：`必须winning-chart打头，winning-bar代表柱状图`<br/>
**data-config说明**：`这里面是一个json对象，url代表后台请求数据接口可以修改成为你自己的`
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
		<link rel="stylesheet" href="winning-visualize-charts.css">
	</head>
	<body>
		<h1>柱状图</h1>
		<div class="winning-chart winning-bar" data-config="{url: 'chart.do?getBar'}" style="height: 450px;"></div>
		<script type="text/javascript" src="echarts.min.js"></script>
		<script type="text/javascript" src="winning-visualize-charts.js"></script>
	</body>
</html>

```

## 后台安装
### SDK安装
SDK已经上传到`公司maven私服`上面，直接POM文件中引入依赖
 ``` maven
<dependency>
	<groupId>winning</groupId>
	<artifactId>bi-structure-charts</artifactId>
	<version>最新版本</version>
</dependency>
 ```
 ### 完整示例
后台接口，`这里以springmvc为例`，封装柱状图
```java
@RequestMapping(params = "getBar", method = RequestMethod.POST)
@ResponseBody
public Object getBar(HttpServletRequest request, HttpServletResponse response, ChartModel chartData)
		throws Exception {

	List<String> legendNameData = new ArrayList<String>();
	List<Object> seriesDataList = new ArrayList<Object>();

	// 轴数据
	List<String> axisData = new ArrayList<String>();
	axisData.add("一月");
	axisData.add("二月");
	axisData.add("三月");
	axisData.add("四月");

	// 展示数据
	List<LineData> seriesData = new ArrayList<LineData>();
	seriesData.add(new LineData("1200"));
	seriesData.add(new LineData("5200"));
	seriesData.add(new LineData("2200"));
	seriesData.add(new LineData("4200"));
	seriesDataList.add(seriesData);
	legendNameData.add("门诊收入");

	// 处理数据
	chartData.axisData(axisData).legendName(legendNameData);
	Option option = ChartOptionUtils.setSeries(chartData, seriesDataList);
	// 标题和副标题 可以不需要
	option.title().text("门诊收入");

	// 返回数据
	return ResultUtils.success(option);
}
```