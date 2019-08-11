## Usage
### long string

Reference: [python - Pythonic way to create a long multi-line string - Stack Overflow](https://stackoverflow.com/questions/10660435/pythonic-way-to-create-a-long-multi-line-string)

* Using `'''`

```
>>> archer_quote = '''
... Emiya Shirou! Listen, you are not "one who fights." You are nothing more than
... "one who creates." Don't think of irrelevant things. There is only one thing
... you can do, master that one thing. Do not forget. The thing you image is
... always "your strongest self." You don't need any other enemies. The opponent
... you have to fight is none other than "your own image."
... '''
>>> archer_quote
'\nEmiya Shirou! Listen, you are not "one who fights." You are nothing more than\n"one who creates." Don\'t think of irrelevant things. There is only one thing\nyou can do, master that one thing. Do not forget. The thing you image is\nalways "your strongest self." You don\'t need any other enemies. The opponent\nyou have to fight is none other than "your own image."\n'
```
```
>>> archer_quote = '''Emiya Shirou! Listen, you are not "one who fights." You are
...                   nothing more than "one who creates." Don't think of
...                   irrelevant things. There is only one thing you can do, master
...                   "your strongest self." You don't need any other enemies.
...                   The opponent you have to fight is none other than
...                   "your own image."'''
>>> archer_quote
'Emiya Shirou! Listen, you are not "one who fights." You are\n                  nothing more than "one who creates." Don\'t think of\n                  irrelevant things. There is only one thing you can do, master\n                  "your strongest self." You don\'t need any other enemies.\n                  The opponent you have to fight is none other than\n                  "your own image."'
``` 


* Using `\`

```
>>> archer_quote = 'Emiya Shirou! Listen, you are not "one who fights." You are ' \
...                'nothing more than "one who creates." Don\'t think of ' \
...                'irrelevant things. There is only one thing you can do, '\
...                'master that one thing. Do not forget. The thing you image ' \
...                'is always "your strongest self." You don\'t need any other ' \
...                'enemies. The opponent you have to fight is none other than ' \
...                '"your own image."'
>>> archer_quote
'Emiya Shirou! Listen, you are not "one who fights." You are nothing more than "one who creates." Don\'t think of irrelevant things. There is only one thing you can do, master that one thing. Do not forget. The thing you image is always "your strongest self." You don\'t need any other enemies. The opponent you have to fight is none other than "your own image."'
```

* Using `(` and `)` ( I prefer this style) 

```
>>> archer_quote = ('Emiya Shirou! Listen, you are not "one who fights." You are '
...                 'nothing more than "one who creates." Don\'t think of '
...                 'irrelevant things. There is only one thing you can do, '
...                 'master that one thing. Do not forget. The thing you image is '
...                 'always "your strongest self." You don\'t need any other '
...                 'enemies. The opponent you have to fight is none other than '
...                 '"your own image."')
>>> archer_quote
'Emiya Shirou! Listen, you are not "one who fights." You are nothing more than "one who creates." Don\'t think of irrelevant things. There is only one thing you can do, master that one thing. Do not forget. The thing you image is always "your strongest self." You don\'t need any other enemies. The opponent you have to fight is none other than "your own image."'
```
