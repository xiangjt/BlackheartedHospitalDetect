

# BlackheartedHospitalDetect
本项目是为[BlackheartedHospital][1]项目提供莆田医院检测支持，在浏览器中通过注入js脚本，自动检测当前搜索引擎中的莆田医院，然后在搜索结果页中插入了莆田系医院标记，提醒用户，避免用户上当受骗。

------

- js脚本介绍
  - ***putian_mobile_detect.js*** 为移动版本搜索引擎提供服务，支持[百度][2]，[神马][3]，[搜狗][4] 移动版本，目前已经在[海豚浏览器中文版][5]中使用。
  - ***putian_desktop_detect.js*** 为桌面版搜索引擎提供服务，支持[百度][6] 桌面版本，目前在chrome插件[Dolphin security helper][7]中使用。
- 使用方法
  - 两个js脚本中都有一个`function __isBlackHospital(url)` 函数，用于判断当前传进来的url是否为莆田医院，参数 `url`可以为字符串，如"湖北省荣军医院"，也可以为url，如"hbsrjyy.com"，用户可以根据项目[BlackheartedHospital][8]提供的数据自行判断，默认返回true，如果用户要使用这个项目，必须重写这个函数。
  - 对于android 浏览器，可以通过`WebView.addJavaScriptInterface` 对js提供一个接口，如`BlackHospital.isBlackHospital(String url)`，通过java层判断是否为莆田医院，至于js脚本的注入时机，可以选择在`WebViewClient.onPageFinished(WebView view, String url) `中通过`WebVIew.evaluateJavascript(String script, ValueCallback<String> resultCallback)`注入
  - 针对桌面版搜索引擎，可以通过把[BlackheartedHospital][9]中的所有医院数据都放在js文件中，通过js判断，但可能会影响效率。


# 截图 #



  [1]: https://github.com/TeamDolphin/BlackheartedHospital
  [2]: http://m.baidu.com
  [3]: http://m.sm.cn/
  [4]: http://m.sogou.com/
  [5]: http://cn.dolphin.com/
  [6]: http://www.baidu.com/
  [7]: https://chrome.google.com/webstore/search/dolphin%20ssecurity?hl=en-US
  [8]: https://github.com/TeamDolphin/BlackheartedHospital
  [9]: https://github.com/TeamDolphin/BlackheartedHospital