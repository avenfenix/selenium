# Selenium Termux

When
```
pip3 install selenium
```

ImportError: dlopen failed: library "libexpat.so.1" not found

Fix

```
pkg up -y && pkg rei libexpat
```



https://www.reddit.com/r/termux/comments/16dzkhg/libexpatso1_not_found_termux/
## Referencias

- [Selenium en termux - tecnobillo](https://tecnobillo.com/sections/bonus/termux/sections/selenium-en-termux/selenium-en-termux.html) 

# Selenium Raspberry PI
Intentando correr Selenium en una Raspberry Pi 4B armv8

### Electron chromedriver

```
wget https://github.com/electron/electron/releases/download/v28.0.0-alpha.2/chromedriver-v28.0.0-alpha.2-linux-arm64.zip
```

## Referencias

- [How to compile ChromeDriver ARM??](https://stackoverflow.com/questions/38732822/compile-chromedriver-on-arm)
- [Electron - Github](https://github.com/electron/electron)
- [Electron Chromedrivers](https://github.com/electron/electron/releases)
- [How to run selenium using python on raspberry pi](https://patrikmojzis.medium.com/how-to-run-selenium-using-python-on-raspberry-pi-d3fe058f011)
