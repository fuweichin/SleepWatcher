# SleepWatcher (Windows Service)

This project is a Windows portion of [macOS SleepWatcher](https://www.bernhard-baehr.de/)

Assisted by Google AI, but I lost the local source code.



## Install

Run install.bat to install the service.

By default the service will start automatically, you may set the service to start manually if necessary.



## Configure

Edit config.ini, by default `script_type` is to `cmd`, you may change `script_type` to any of `sh`, `powershell`, `python` or `node`, and edit you subsequent sleep/wakeup scripts.

If your script takes long time to run, you may need to set a larger `script_timeout` and to add `set-WaitToKillServiceTimeout-to-5000.reg` to Windows Registry

```ini
# SleepWatcher Configuration

script_type=cmd
script_timeout=5000

[sh]
exe_path=C:\Program Files\Git\bin\bash.exe
wakeup_script=.wakeup
sleep_script=.sleep

[cmd]
exe_path=C:\Windows\System32\cmd.exe
wakeup_script=.config\sleepwatcher\wakeup.bat
sleep_script=.config\sleepwatcher\sleep.bat

[powershell]
exe_path=AppData\Local\Microsoft\WindowsApps\pwsh.exe
wakeup_script=.config\sleepwatcher\wakeup.ps1
sleep_script=.config\sleepwatcher\sleep.ps1

[python]
exe_path=AppData\Local\Python\bin\python3.exe
wakeup_script=.config\sleepwatcher\wakeup.py
sleep_script=.config\sleepwatcher\sleep.py

[node]
exe_path=C:\Program Files\Node.js\node.exe
wakeup_script=.config\sleepwatcher\wakeup.js
sleep_script=.config\sleepwatcher\sleep.js

```



## Start and Stop

Run start.bat to start the service manually.
run stop.bat to stop the service manually.



## Uninstall

Run uninstall.bat
