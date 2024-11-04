# TorHidden
TorHidden - A simple proxy tool.

![GitHub repository](https://img.shields.io/badge/raic0d3r-TorHidden-blue?style=flat-square&logo=github)
![GitHub version](https://img.shields.io/badge/version-1.0-yellow?style=flat-square)

TorHidden - A simple proxy tool.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Example](#example)
- [Help](#help)
- [Features](#features)
- [Environments](#environments)
- [Disclaimer](#disclaimer)
- [Author](#author)
- [License](#license)

## Installation For Windows

1. Clone the repository
    ```
    git clone https://github.com/raic0d3r/TorHidden.git
    ```
2. unpack the Tor folder to the root of drive.
    ```
    Example : C:\Tor\
    ```

3. unpack the Tor folder to the root of drive C.
    ```
    C:\Tor\
    ```
    
4. Create torrc file
    ```
    echo( > C:\Tor\torrc
    ```
    To test if the service with the settings file will start correctly:
    ```
    C:\Tor\tor.exe -f "C:\Tor\torrc"
    ```
5. Now install the Tor service, which will read the settings from the C:\Tor\torrc file:
    ```
    C:\Tor\tor.exe --service install -options -f "C:\Tor\torrc"
    ```
    
6. By default, the Tor service listens on port 9050, so you can check whether it is started by a command that shows if port 9050 is listened:
    ```
    for /f "tokens=1,2,3,4,5*" %i in ('netstat -aon ^| findstr ":9050" ^| findstr /i listening') do echo %j %l & @tasklist | findstr %m
    ```    
    
## Usage

    C:\Tor\tor.exe --service start
    C:\Tor\tor.exe --service stop
    C:\Tor\tor.exe --service stop
    C:\Tor\tor.exe --service remove
    
## Example
  1. Write Proxies
  ```
  proxies = {
    'http': 'socks5://localhost:9050',
    'https': 'socks5://localhost:9050'
  }
  ```
  2. Call New Proxy
  ```
  def renew_tor_ip():
    with Controller.from_port(port=9051) as controller:
        controller.authenticate()
        controller.signal(Signal.NEWNYM)
  ```
  3. Example of code using proxy :
  ```
  def checkmyip(url): 
      for x in range(1):
          renew_tor_ip()
          ipAddresss = requests.get("http://api.ipify.org", proxies=proxies).text 
          print('Current IP: '+ ipAddresss) 
        
  ```

## Features

   - [x] Hidden Proxy for Python Requests

## Environments

* Windows
* Linux
* macOS
* Android (Termux)

## Disclaimer

:warning: We are not responsible for any misuse or damage caused by this program. use this tool at your own risk!

## Author

by [**Raihan Uddin**](https://t.me/raic0d3r)

([Table of Contents](#table-of-contents))

## License

This repository is under [Unlicense License](https://github.com/raic0d3r/TorHidden/blob/main/LICENSE).
