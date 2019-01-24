# 链家挂牌数据爬虫 - Scrapy项目

## 运行指南
### 普通运行方式
- `cd scrapy_housing`
- `scrapy crawl lianjia_spider`


### 使用scrapyd控制
- 打开`./scrapy.cfg`，去掉url前的注释
- `pip install scrapyd`
- `scrapyd -deploy -l`
- `scrapyd`
#### 使用scrapyweb
- `pip install scrapydweb`
- `scrapydweb -ss 127.0.0.1:6800`
- `scrapydweb`
