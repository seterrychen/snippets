## Installation
Debian/Ubuntu Python3
```
$ sudo apt-get install -y python3-dev python3-pip libxml2-dev libxslt1-dev zlib1g-dev libffi-dev libssl-dev
$ pip install scrapy
```

## [Documents](https://docs.scrapy.org/en/latest/index.html)
### Tutorial
* [Scrapy爬蟲與資料處理30天筆記](https://ithelp.ithome.com.tw/users/20107514/ironman/1919)
* [Scrapy: Powerful Web Scraping & Crawling with Python](https://www.udemy.com/course/scrapy-tutorial-web-scraping-with-python/)

## [Tips](https://blog.scrapinghub.com/2016/08/25/how-to-crawl-the-web-politely-with-scrapy)

## Usage
### Parsing xml
```
response.selector.register_namespace('d', 'http://www.sitemaps.org/schemas/sitemap/0.9')
response.xpath('//d:loc')
```
