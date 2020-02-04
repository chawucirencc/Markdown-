`redis`：使用 `redis-server.exe` 启动服务。前提是将 `redis` 添加到系统环境变量中。

##### 使用 Python 操作 `redis`： #####

```python
def operating_redis():
    try:
        pool = redis.ConnectionPool(host='localhost', port=6379, decode_responses=True)	# 连接池
        r = redis.Redis(connection_pool=pool)
        r.set('name', 'name1')	# 字符串的操作
        # print(r['name'])
        print(r.get('key1'))
        print(type(r.get('key1')))
    except Exception as err:
        print(err)
```

连接池管理对于所有的 `redis server` 的连接，避免每次建立连接和释放连接的开销。默认，每个 `redis` 实例都会维护自己的连接池。这里先建立一个连接池，然后作为 `redis.Redis()` 的一个参数，可以实现一个多个实例共享一个连接池。

##### **关于`scrapy redis`** ： #####

在使用 `scrapy` 框架的时候，官方并不支持多个同时采集一个站点，有一个比较传统的办法，就是将所要爬取的 `url` 集合分成几个部分，然后交给几个不同的 `scrapy` 去爬取。虽然可以达到效果，但是比较复杂！