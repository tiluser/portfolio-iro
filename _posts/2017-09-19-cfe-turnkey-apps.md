---
layout: post
title: Turnkey apps with Excel 
---

In their Professional Excel Development, Rob Bovey, Dennis Wallentin, Stephen Bullen, and John Green discuss "dictator applications" which take control of the entire Excel
environment in favor of presenting an interface where the user can essentially forget about Excel. This idea is especially useful for creating single-purpose applications which
hides the underlying complexity of the task. 

While it's possible to develop these types of applications in Excel, it requires additional setup work which can be complex. What needs to be done?

1. A dictator application must not alter the current Excel environment, so it needs to save the current settings, set up the environment according to its own needs, and then
restore the original settings on exit. 

2. On startup, it should hide any unneeded functionality, including the menu and unneeded tabs. 

If the spreadsheet is compiled into an executable, it further reduces the awareness of the end user that he is dealing with the Excel environment. The following code can be 
used to open the application directly into a dialog box and bypass the spreadsheet tabs:

Private Sub Auto_Open()
    Application.ScreenUpdating = False
    Application.WindowState = xlMinimized
    Application.Visible = False
    Call MVCImportExportStartup
End Sub

The Auto_Close() method will close up the app, ensure that memory is freed, and bypass the default Save dialog. 

There are various tools available for compiling an Excel spreadsheet into a distributable exe application. The DoneEx plugin offers advantages such as bypassing the default
Excel splash screen and removing the ability for the end user to view the source code. 


