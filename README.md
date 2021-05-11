# Batch_script_automatically_login_website_and_maintain_log
@if (@CodeSection == @Batch) @then

 

 

@echo off

exit | clip

:: Informatica login check

set SendKeys=CScript //nologo //E:JScript "%~F0"

START chrome "https://test.com"

timeout /t 5

sleep 2

%SendKeys% "{A}"

%SendKeys% "{d}"

%SendKeys% "{m}"

%SendKeys% "{i}"

%SendKeys% "{n}"

%SendKeys% "{i}"

%SendKeys% "{s}"

%SendKeys% "{t}"

%SendKeys% "{r}"

%SendKeys% "{a}"

%SendKeys% "{t}"

%SendKeys% "{o}"

%SendKeys% "{r}"

%SendKeys% "{TAB}"

%SendKeys% "{A}"

%SendKeys% "{d}"

%SendKeys% "{m}"

%SendKeys% "{i}"

%SendKeys% "{n}"

%SendKeys% "{i}"

%SendKeys% "{s}"

%SendKeys% "{t}"

%SendKeys% "{r}"

%SendKeys% "{a}"

%SendKeys% "{t}"

%SendKeys% "{o}"

%SendKeys% "{r}"

%SendKeys% "{ENTER}"

timeout /t 5

sleep 3

%SendKeys% "^{l}"

%SendKeys% "^{c}"

start notepad "d:\DEV\test.txt"

%SendKeys% "^{v}"

%SendKeys% "^{s}"

 

set i= login successfull for Informatica DEV 4.4

set f= login failed

set date = %date%

set time = %time%

findstr /m "https://test.com" test.txt

if %errorlevel%==0 (

echo ******************%i%******************>"d:\DEV\log.txt"

echo 'DATE'%date%>>"d:DEV\log.txt"

echo 'TIME'%time%>>"d:\DEV\log.txt"

)else (

echo ******************%f%******************>"d:\DEV\log.txt"

echo 'DATE'%date%>>"d:DEV\log.txt"

echo 'TIME'%time%>>"d:DEV\log.txt"

)

 

:: Analytics login check

timeout /t 2

sleep 3

set SendKeys=CScript //nologo //E:JScript "%~F0"

START chrome "http://analytics"

timeout /t 5

%SendKeys% "{TAB}"

%SendKeys% "{A}"

%SendKeys% "{d}"

%SendKeys% "{m}"

%SendKeys% "{i}"

%SendKeys% "{n}"

%SendKeys% "{i}"

%SendKeys% "{s}"

%SendKeys% "{t}"

%SendKeys% "{r}"

%SendKeys% "{a}"

%SendKeys% "{t}"

%SendKeys% "{o}"

%SendKeys% "{r}"

%SendKeys% "{TAB}"

%SendKeys% "{A}"

%SendKeys% "{d}"

%SendKeys% "{m}"

%SendKeys% "{i}"

%SendKeys% "{n}"

%SendKeys% "{1}"

%SendKeys% "{2}"

%SendKeys% "{3}"

%SendKeys% "{ENTER}" 

 

timeout /t 5

%SendKeys% "^{l}"

%SendKeys% "^{c}"

start notepad "d:DEV\test.txt"

%SendKeys% "^{v}"

%SendKeys% "^{s}"

 

 

set k= login successfull for OBIEE DEV 4.4

set l= login failed

set date = %date%

set time = %time%

findstr /m "http://test.com" test.txt

if %errorlevel%==0 (

echo ******************%k%******************>>"d:\test\log.txt"

echo 'DATE'%date%>>"d:\test\log.txt"

echo 'TIME'%time%>>"d:\test\log.txt"

)else (

echo ******************%l%******************>>"d:\test\log.txt"

echo 'DATE'%date%>>"d:\test\log.txt"

echo 'TIME'%time%>>"d:\test\log.txt"

)

 

del "d:DEV\test.txt"

echo.>"d:DEV\test.txt"

@end

 

// JScript section

var WshShell = WScript.CreateObject("WScript.Shell");

WshShell.SendKeys(WScript.Arguments(0));
