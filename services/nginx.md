# Reference

* [Variable index](http://nginx.org/en/docs/varindex.html)


## Cache setting
```
location / {
    # kill cache
    add_header Last-Modified $date_gmt;
    add_header Cache-Control 'no-store, no-cache, must-revalidate, proxy-revalidate, max-age=0';
    if_modified_since off;
    expires off;
    etag off;
}
```

## multiple location
```
location ~ ^/(first/location|second/location)/ {
  ...
}
```
