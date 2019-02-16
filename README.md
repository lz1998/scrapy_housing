# 链家挂牌数据爬虫 - Scrapy项目

## 运行指南
### 普通运行方式
- `cd scrapy_housing`
- `scrapy crawl lianjia_spider`


### 使用scrapyd控制
- 打开`./scrapy.cfg`，去掉url前的注释
- `pip install scrapyd` docs: [scrapyd](https://scrapyd.readthedocs.io/en/stable/overview.html)
- `pip install scrapyd-client` docs: [scrapyd-client](https://github.com/scrapy/scrapyd-client)
- `scrapyd-deploy -l`
- `scrapyd` 启动[服务器](http://localhost:6800)，端口：6800
- `curl http://localhost:6800/schedule.json -d project=default -d spider=lianjia_spider` 启动爬虫
- `curl http://localhost:6800/cancel.json -d project=default -d job=jobid_responsed_by_server` 停止爬虫


#### 使用scrapyweb
- `pip install scrapydweb`
- `scrapydweb -ss 127.0.0.1:6800`
- `scrapydweb`
