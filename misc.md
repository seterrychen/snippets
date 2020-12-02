# Tools
## APT packages
* [UbuntuUpdates - All package updates](https://www.ubuntuupdates.org/)

## Web
* [簡單易懂的 OAuth 2.0 - Speaker Deck](https://speakerdeck.com/chitsaou/jian-dan-yi-dong-de-oauth-2-dot-0)
* [MDN Web Docs - Mozilla](https://developer.mozilla.org/zh-TW/)
* [Wayback Machine - Internet Archive](https://web.archive.org/)
* [Crop a Circle in image online](https://crop-circle.imageonline.co/)
* [Color Hunt - Color Palettes for Designers and Artists](https://colorhunt.co/)
* [12 Best Tools for Playing Around with Color](https://medium.muz.li/12-best-tools-for-playing-around-with-color-1cdbed08e362)
* [免費線上Logo設計，商標製作工具– DesignEvo](https://www.designevo.com/tw/)

## Markdown
* [To generate table of content](https://github.com/thlorenz/doctoc)
* [GitHub Readme Instant Preview](https://github.com/joeyespo/grip)

## Others
* Test website speed
```
$ cat curl-format.txt
    time_namelookup:  %{time_namelookup}\n
       time_connect:  %{time_connect}\n
    time_appconnect:  %{time_appconnect}\n
      time_redirect:  %{time_redirect}\n
   time_pretransfer:  %{time_pretransfer}\n
 time_starttransfer:  %{time_starttransfer}\n
                    ----------\n
         time_total:  %{time_total}\n

$ curl -w "@curl-format.txt" -o /dev/null -s -L "http://cizixs.com"
    time_namelookup:  0.012
       time_connect:  0.227
    time_appconnect:  0.000
      time_redirect:  0.000
   time_pretransfer:  0.227
 time_starttransfer:  0.443
                    ----------
         time_total:  0.867
```

time_connect: TCP Three-way Handshake
time_appconnect: TLS setup
time_redirect: is the time took for all the redirect steps to complete
time_pretransfer: is the time from start to before the file transfer just about to begin, including all pre-transfer commands and negotiations
time_starttransfer: is the time it took from the start to the first byte about to be transferred

example https://blog.cloudflare.com/content/images/2018/10/Screen-Shot-2018-10-16-at-14.51.29-1.png

* [what is the english name of special characters](http://forum.wordreference.com/threads/what-is-the-english-name-of-special-characters.101066/)
```
~  = tilde
!  = exclamation mark
() = parentheses
-  = hyphen
_  = underscore
[] = square brackets
{} = curly brackets (is there something more "official"? braces?)
\  = backslash
/  = slash, solidus
<> = angle brackets
*  = asterisk
&  = ampersand
^  = caret
```
