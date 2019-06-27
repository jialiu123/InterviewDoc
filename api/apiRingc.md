## 运行效果
![柱状图](../static/images/ringc.jpg)
## 代码demo
前台html
```html
<div class="winning-chart winning-ringc" data-config="{url: 'chart.do?getRingc'}" style="height: 330px;"></div>
```
---

后台接口：`这里以springmvc为例`
```java
@RequestMapping(params = "getRingc", method = RequestMethod.POST)
@ResponseBody
public Object getRingc(HttpServletRequest request, HttpServletResponse response, ChartModel chartData)
		throws Exception {

	List<Object> seriesDataList = new ArrayList<Object>();

	List<RingcData> seriesData = new ArrayList<RingcData>();
	seriesData.add(new RingcData("测试环形图", "12", "元"));
	seriesDataList.add(seriesData);

	Option option = ChartOptionUtils.setSeries(chartData, seriesDataList);

	return ResultUtils.success(option);
}
```