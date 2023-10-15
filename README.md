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

ChatGPT adapto un tutorial de la Raspberry Pi a Termux. 


Para ejecutar el mismo código en Termux sin proot y sin el uso de un monitor, puedes seguir estos pasos:

1. **Instala Python y pip:**
   ```
   pkg install python
   pkg install python-dev
   pkg install clang
   pkg install libcrypt
   pkg install libxml2
   pkg install libxslt
   pkg install libiconv
   pkg install libjpeg-turbo
   pkg install libxslt
   pkg install ffmpeg
   pkg install nodejs-lts
   pip install --upgrade pip
   ```

2. **Instala ChromeDriver:**
   Puedes descargar ChromeDriver directamente en Termux y añadir la ubicación al PATH del sistema. Primero, obtén el enlace de descarga de ChromeDriver compatible con tu arquitectura y Android desde el sitio oficial de ChromeDriver: https://sites.google.com/a/chromium.org/chromedriver/downloads

   Luego, descarga y descomprime ChromeDriver en un directorio de tu elección en Termux.

3. **Instala las dependencias de Python:**
   ```
   pip install pyvirtualdisplay selenium
   ```

4. **Modifica el código:**
   Utiliza la ubicación donde has descargado ChromeDriver en el código. Además, asegúrate de que no estás usando 'sudo' ya que Termux no requiere privilegios de superusuario para ejecutar este código.

   ```python
   from pyvirtualdisplay import Display
   from selenium import webdriver

   # Ruta a ChromeDriver en Termux
   chrome_driver_path = '/path/to/your/chromedriver'

   # Configurar el navegador Chrome
   options = webdriver.ChromeOptions()
   options.add_argument('--no-sandbox')
   options.add_argument('--disable-dev-shm-usage')
   options.add_argument('headless')  # Para ejecutar en modo headless (sin interfaz gráfica)

   # Iniciar el display virtual
   display = Display(visible=0, size=(800, 600))
   display.start()

   # Iniciar el navegador Chrome
   driver = webdriver.Chrome(executable_path=chrome_driver_path, options=options)

   # Ahora puedes usar el navegador Chrome en modo headless sin necesidad de un monitor.
   ```

Asegúrate de reemplazar `'/path/to/your/chromedriver'` con la ruta donde hayas descargado ChromeDriver en Termux. Ahora puedes ejecutar este script en Termux para utilizar Chrome en modo headless sin necesidad de un monitor.

No es necesario tener Chrome instalado en Termux para usar Selenium en Termux. Selenium es una herramienta de automatización web que permite controlar navegadores web desde programas Python u otros lenguajes de programación. Puedes utilizar Selenium con otros navegadores compatibles como Firefox o incluso sin un navegador gráfico (modo headless) para realizar automatizaciones web en Termux sin necesidad de instalar Chrome en el sistema. Solo necesitas tener instalado Python, Selenium y un controlador adecuado (como ChromeDriver o GeckoDriver para Firefox) para comenzar a automatizar acciones en la web desde Termux.
## Referencias

- [x](https://www.reddit.com/r/termux/comments/16dzkhg/libexpatso1_not_found_termux/) 
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
