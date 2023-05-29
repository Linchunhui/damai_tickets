# 大麦网抢票脚本
> 2023.05.29 
> 默认config为2023五月天杭州站6.18场，2人票

PS：
 - time_interval可以设置高一点，防止被反爬虫；
 - 谷歌浏览器和chromdriver推荐下载老版本比如88、90

## Chromedriver 修改

1. 下载Hexedit或者使用Vscode中的Hexedit插件
2. 使用Hexedit打开chromedriver.exe 
3. 搜索 `$cdc_`
4. 更改为任意其他字符串，如`$cxx_`


## 配置文件

```json
{
    "date": [1],
    "sess": [1],
    "price": [2],	
    "real_name": [1],
    "nick_name": "",
    "ticket_num": 3,
    "driver_path": "./chromedriver",  # windows 填 ./chromedriver.exe
    "damai_url": "https://www.damai.cn/",
    "target_url": "https://m.damai.cn/damai/detail/item.html?itemId=704494827883&spm=a2o71.category.itemlist.ditem_3"
}

```

- target_url 抢票的网页，必须是移动端网页，即m.damai.cn域名下的网页。
- damai_url 一般不需要更改，用于登录
- ticket_num 抢票张数
- date 日期 这个版本未测试包含日期筛选的网页，目前大概率不可用
- sess 场次，对应买票页面弹框的场次，1代表第一个按钮，数组表示多个可选项
- price 价位，对应买票页面弹框的价格，1代表第一个按钮，数组表示多个可选
- driver_path 对应当前电脑Chrome浏览器版本的驱动文件
- real_name 结算页面选择第几个实名的人
- nick_name 没什么用

## 注意事项

1. 账号必须先做好实名制认证，并添加至少一个实名制的人的信息
2. 第一次打开后会进入登录页面，需要手动选择扫码登陆
3. 如果太久没用，需要先清空目录下的 cookie 文件，然后在重新登录
