# mobiscroll 时间选择器小结
## mobiscroll 简介
mobiscroll 是一系列的 UI 控件集合，其面向网页与移动开发者，以将开发人员从繁琐枯燥的 UI 控件编码工作中解放出来，而将更多的精力投入业务及其他需求的编码实现中去。mobiscroll 支持 Javascript、jQuery、Angular、React 等语言，并且包含有日历、时间选择器、颜色选择器、表单、图像、列表等较多的控件，各个控件下载和的具体使用方法可以访问其[官方网站](https://mobiscroll.com/)。

## mobiscroll 时间选择器的简单用法
版本 3.2.4 的 mobiscroll 需要 jQuery 的版本在 1.7 版本及以上，并且其支持 Android 4.1+ 、iOS 6+ 、Windows Phone 10 以及大多数的移动与桌面浏览器。

1. 在官网下载时间选择器控件的相应资源
2. 在自己的项目中的引入资源

	```
	<!-- 引入 jQuery 插件 -->
	<script src="jquery-2.2.2.min.js"></script>
	<!-- 引入 Mobiscroll -->
	<script src="js/mobiscroll.custom-3.2.4.min.js"></script>
	<link href="css/mobiscroll.custom-3.2.4.min.css" rel="stylesheet" type="text/css">
	```
3. 添加 input 标签到相应的 HTML 文档中
	
	```
	<input id = 'datePicker' />
	<input id = 'timePicker' />
	<input id = 'datetimePicker' />
	```
4. 使用默认参数创建时间选择器控件

	```
	// 生成日期选择器
	$("#datePicker").mobiscroll().date();
	// 生成时间选择器
	$("#timePicker").mobiscroll().time();
	// 生成日期时间选择器
	$("#datetimePicker").mobiscroll().datetime();
	```
5. 自定义参数创建时间选择器
	
	在创建时间选择器时，可以传入参数来确定选择器的样式、显示方式、响应事件、语言、日期格式等等属性。其基本用法如下：
	
	```
	// 创建选择器时，指定参数
	$("#datePicker").mobiscroll().date({ 
        theme: 'ios', 
        display: 'bottom',
        animate: 'swing',
        rows: 5,
        lang: 'zh',
        dateformat: 'yy-mm-dd',
        onBeforeShow: function (event, inst) {
          console.log('before show date picker')
		}
    });
	```
	除了设置选择器的属性外，还可以调用时间选择器的方法，基本用法如下：
	
	```
	// 销毁选择器，将 HTML 元素重置
	$('#datePicker').mobiscroll('destroy');
	
	// 获取选择器对象
	var scoller = $('#datePicker').mobiscroll('getInst');
	```
	详细的属性及方法可以参考[官方文档](https://docs.mobiscroll.com/jquery/datetime)
	
	[测试页面](./Test-mobiscroll.html)

