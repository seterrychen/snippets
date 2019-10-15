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

## location order
```
location [modifier] uri { ... } 
modifier:  = | ~ | ~* | ^~ 
```

`~*`: modifier (for case-insensitive matching)
`~`: modifier (for case-sensitive matching)
`^~`: If the longest matching prefix location has the `^~ modifier then regular expressions are not checked.

```
location  = / {
  # matches the query / only.
  [ configuration A ] 
}
location  / {
  # matches any query, since all queries begin with /, but regular
  # expressions and any longer conventional blocks will be
  # matched first.
  [ configuration B ] 
}
location /documents/ {
  # matches any query beginning with /documents/ and continues searching,
  # so regular expressions will be checked. This will be matched only if
  # regular expressions don't find a match.
  [ configuration C ] 
}
location ^~ /images/ {
  # matches any query beginning with /images/ and halts searching,
  # so regular expressions will not be checked.
  [ configuration D ] 
}
location ~* \.(gif|jpg|jpeg)$ {
  # matches any request ending in gif, jpg, or jpeg. However, all
  # requests to the /images/ directory will be handled by
  # Configuration D.   
  [ configuration E ] 
}
```

