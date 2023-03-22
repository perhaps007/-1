# 1.功能概述
一卡通后台报表使用FinePrint插件实现静默打印
# 2.设置本地打印功能
1、点击报表>报表web属性>分页预览设置，选择自定义按钮双击添加到工具栏
![1679464460538](https://user-images.githubusercontent.com/42803896/226814681-12937ae5-ba59-4a12-9eaa-e3a1fdd37590.jpg)

2、控件名称设置为【本地打印】

![2](https://user-images.githubusercontent.com/42803896/226815447-d1d3d8fb-c80e-49cc-bb4d-51da5cf820e2.png)


3、点击编辑，设置打印图标

![3](https://user-images.githubusercontent.com/42803896/226815288-7fd55ac1-0bf9-4382-9f1e-49bdab8ac52a.png)


4、选择自定义事假添加如下内容

![4](https://user-images.githubusercontent.com/42803896/226815596-c5fa4c2e-1617-41eb-a6c7-f779615163d0.png)
![5](https://user-images.githubusercontent.com/42803896/226815606-41cc88f5-b448-42b4-8e85-789fd75fba37.png)

# 3.设置打印机

1、问题：当现场某个窗口的默认打印机不能打印报表时，思路：一卡通程序有设置打印机功能（1：小票打印机2：发票打印3：app发票打印机），取一卡通程序设置配置好的打印机来打印报表

![6](https://user-images.githubusercontent.com/42803896/226815699-717e7aaf-e8ad-4164-a07c-78bc21b2ad1a.png)

2、在报表中可以添加如下函数来设置打印机

![7](https://user-images.githubusercontent.com/42803896/226815713-99c499eb-6249-42c8-85b8-b524dd5dd31e.png)

# 4.参考

1、本地打印demo
```js
FR.doNativePrint({
	// 隐藏默认提示框
	hidePrintTip: true,
	// 是否弹窗
	isPopUp: false,
	// 打印指定页面1,3,5-6
	index: 0,
	// 打印份数
	copies: 1,
	// 需要打印的报表url
	//url : url,//不传打印当前报表
	//printerName: printerName) //不传取系统默认打印机
});
```

2、选择打印机demo
```js
function getCookie(name)
{
	// cookie中的数据都是以分号加空格区分开
	var arr = parent.document.cookie.split("; ");
	for (var i = 0; i < arr.length; i++)
	{
		if (arr[i].split("=")[0] == name)
		{
			// 返回值转码
			return decodeURI(arr[i].split("=")[1]);
		}
	}
	// 未找到对应的cookie则返回空字符串
	return '';
}
```

3、FinePrint下载（注意要单独建文件夹，不要和帆软安装在同一目录下 ）
https://github.com/perhaps007/-1/blob/master/FinePrint_windows_8_0.exe
