# printsrv
Ticket printer driver  
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/fd513dfbfcb645b1ac43bc381b4b5482)](https://www.codacy.com/app/mihkel-putrinsh/cardsrv?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Piletilevi/cardsrv&amp;utm_campaign=Badge_Grade)

## Prerequisites

**!NB**
> Make sure that in Python installer, on **Customize Python** screen, You must select
**[Will be installed on local hard drive]** for **[Add python.exe to path]**

- download, extract, and install [python-2.7.12](https://github.com/Piletilevi/printsrv/files/391929/python-2.7.12.zip)  
- download, extract, and install [IronPython-2.7.5](https://github.com/Piletilevi/printsrv/files/391931/IronPython-2.7.5.zip)  
- download, extract, and install [PIL-1.1.7.win32-py2.7](https://github.com/Piletilevi/printsrv/files/391901/PIL-1.1.7.win32-py2.7.zip)  
- download, extract, and install [pywin32-220.win32-py2.7](https://github.com/Piletilevi/printsrv/files/391897/pywin32-220.win32-py2.7.zip)


### Drivers

- Download ticket printer drivers  
  - [RasoASM-0.1.3.zip](https://github.com/Piletilevi/RasoASM/archive/0.1.3.zip)
  - [printsrv-0.2.1-lt-5.zip](https://github.com/Piletilevi/printsrv/archive/0.2.1-lt-5.zip)

- Unpack the contents to C:\plevi folder  
```
C:\plevi\printsrv  
C:\plevi\RasoASM  
```
- execute `C:\plevi\printsrv\install.bat`  

There is an issue with IronPython installation. It doesnot register to windows path variable, so we included registration command into install.bat (that You just executed). Everything should be ok now, but on some windows systems it keeps forgetting the new path.  
To verify, that IronPython is correctly set up, open cmd and run `PATH` command. It will return all the registered system paths - look, if **IronPython 2.7** is also there.  
If it is not, then You have to open System Environment Variables from Control Panel and append to the end of PATH variable value `;%PROGRAMFILES%\IronPython 2.7`

Also You should verify pip modules with
`C:\Users\Kasa>pip list`
and output should look like
> fontname (0.2.0)  
freetype-py (1.0.2)  
github3.py (0.9.5)  
PIL (1.1.7)  
pip (8.1.2)  
pywin32 (220)  
qrcode (5.3)  
requests (2.10.0)  
setuptools (20.10.1)  
six (1.10.0)  
uritemplate.py (0.3.0)  
WMI (1.4.9)  

### Configuration

- register .plp files in Windows to be opened automatically with `C:\plevi\printsrv.exe`  
- Salespoint ID must be unique and written to `C:\plevi\persistent.ini` file with syntax 'LT_/salespoint_name/'
  example: my_id = LT_kauno_maxima_01
- please make sure, that the ticket printer name in `C:\plevi\persistent.ini` and `C:\plevi\setup_lt.ini` is the same, as in Windows (Devices and printers) and page size in printer settings is 'Letter'
- make a test sale of ticket with successful transaction confirmation - then also the receipt is printed


### Special note

Please make sure, that connected wires are connected in same order over all installations.
Also make sure port mapping is identical everywhere.  

Even better
- create a document, where required wiring and port mapping is described and every time someone drives to point of sale to install the printers, give these instructions along.  
- label the wires. get a permanent marker or buy labeling machine
- take a photo of correctly connected wires at every POS

Thank us later.  
M-O-O-R
