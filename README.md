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
- `logparser` 用logparser来解析log文件，提供统计信息，在`./logs/`下会出现`stats.json`


#### 使用scrapyweb
- `pip install logparser`
- `vim ~/anaconda3/lib/python3.6/site-packages/logparser/settings.py`，修改29行`SCRAPYD_LOGS_DIR = '/Users/somebody/PycharmProjects/scrapy_housing/logs/'`，确保log文件记录在当前scrapyd项目下。注意：必须写成'/Users/somebody/...'而不能写'~/...'，具体原因还不知道。
- `pip install scrapydweb`
- `scrapydweb -ss 127.0.0.1:6800`
- `scrapydweb`
