
基于TradingView本地SDK的可视化前后端代码，适用于缠论量化研究，和其他的基于几何交易的量化研究。

参考文章：文章连接
在线体验：http://162.14.82.169:8134/

https://github.com/ibaihuo/chanvis/blob/main/pics/sz000001.jpg

## 架构体系
1. 使用TradingView的本地SDK做可视化，支持本地或者云平台部署。
1. 前端使用vue和typescript来实现的画图的功能和接口。
2. 后端使用Python的Web框架Flask，提供api接口。
3. 使用MongoDB来存储K线的历史数据，缠论识别出来的结构数据。


## 功能点
1. 实现了在TradingView的界面上，自定义按钮（button)，实现画笔、线段、中枢的功能；
2. 实现了自定义指标的功能点；
3. 完美的继承了在线TradingView的大部分功能（因为sdk版本的功能，要落后与在线的版本一点）；
4. 没有画图数量的限制；
5. 可以完全的自定义各种数据点，实现自己的千人千缠的需求；
6. 可以保存画的图，后续加载使用（暂未添加，可以直接使用TV官方的一个代码，基于Django和Postgresql实现）；
7. 实现逐K回放的功能（使用较复杂，暂未添加）；

## 目录结构说明
```bash
├── README.md
├── api               # API目录
│   ├── chanapi.py    # 核心的接口代码
│   ├── requirements.txt  # python的包依赖
│   ├── symbol_info.py    # 加载票的名字，开源通过TV界面搜索
├── comm
│   ├── __init__.py
│   └── conf.py       # 配置信息
├── data              # mongodb的数据，使用后面的：hetl/hmongo/restore_chanvis_mongo.sh 导入本目录的数据
│   ├── config
│   ├── nlchan
│   └── stock
├── hetl             # K线history 的 ETL相关
│   ├── hmgo         # mongo数据库相关
│   ├── selcoin      # 选币相关
│   └── stock        # 股票相关
├── pics             # 图片目录
│   └── sz000001.jpg
├── ui
│   ├── README.md     # 说明，安装npm的库，启动
│   ├── package.json  # 库的版本
│   ├── public        # 需要把官方的charting_library/和datafeeds/目录复制到此处
│   ├── src           # 前端源代码，主要是：src/components/ChanContainer.vue
└── utils
    ├── __init__.py
    ├── dtlib.py      # 日期相关的辅助函数
    └── nlchan.py     # naturalchan相关的辅助函数
```

## 已知bug
1. 本程序已发现一些bug，就是目前是全量画线的功能，当K线还没有加载出来的时候，画线就会画在边框，形成一条难看的线。刷新整个页面再来吧。
2. 本人主要做数据挖掘，使用Python。并不熟悉前端，包括vue和js，全是用到一点去搜索一点，因此代码仅供参考。
3. 当然，非常欢迎专业前端参与贡献，这样好多想法应该都可以实现。

## 缠论说明

本代码目前提供了一个可用的demo系统，可以按自己的需求，来参照里面的部分实现，去完成每个人自己的缠论量化的伟大的事业，去实现自己的千人千缠的可视化。

本人目前走的是缠论的一个小众分支--摩尔缠论，demo里面提供的示例数据也是通过这个策略来实现的，各位只需要参考里面的数据结构、接口、可视化等的实现方式，再根据自己的需求，去优化自己的代码即可。

demo的数据的准确性，各位也不要太在意，这块是我目前还需要不断完善的点，也是我接下来的重点。一个完美的结构，是需要大量的时间去优化和实现的。

本开源的代码，不具有量化策略的功能，也不具备回测等功能，其目的只是提供一个几何分析的可视化工具而已，期望不要太高。

如果对以缠论为代表的几何交易的程序化实现和可视化有需求，也不要期望太低，基于TV的可视化，会给你不一样的体验。

## 联系作者

欢迎对缠论量化有兴趣的伙伴，一起讨论，去实现那完美的几何结构！尤其欢迎一起讨论和共同学习【摩尔缠论】。

加好友请备注：自然之缠 （否则不予通过）。
https://github.com/ibaihuo/chanvis/blob/main/pics/quantchan.jpg