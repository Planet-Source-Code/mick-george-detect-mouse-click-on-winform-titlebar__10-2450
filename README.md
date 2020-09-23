<div align="center">

## Detect  mouse click on winform titlebar


</div>

### Description

Left mouse click on a winform titlebar to set the forms opacity to 50% while dragging the form, release the mouse to set the form opacity back to 100%.
 
### More Info
 
This is handy if you have a modal dialog and you want to see something behind the dialog, just click it and move it to set the opacity.

Copy the code below to a Winform class and run it.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Mick George](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/mick-george.md)
**Level**          |Beginner
**User Rating**    |4.5 (50 globes from 11 users)
**Compatibility**  |VB\.NET
**Category**       |[Controls/ Forms/ Dialogs/ Menus](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/controls-forms-dialogs-menus__10-3.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/mick-george-detect-mouse-click-on-winform-titlebar__10-2450/archive/master.zip)

### API Declarations

Thanks to Franci Penov @ MS for pointing me to this C# example http://www.experts-exchange.com/Programming/Programming_Languages/C_Sharp/Q_20701571.html


### Source Code

```
Private Const WM_NCLBUTTONDOWN As Long = &HA1
  Private Const WM_NCLBUTTONUP As Long = &HA0
  Protected Overrides Sub DefWndProc(ByRef m As System.Windows.Forms.Message)
    ' -- You might want to trap for user clicking, min, max or close and ignore
    ' -- Trap left mouse click down on titlebar
    If CLng(m.Msg) = WM_NCLBUTTONDOWN Then
      ' -- Set the forms opacity
      If Me.Opacity <> 0.5 Then Me.Opacity = 0.5
      ' -- Trap left mouse click up on titlebar
    ElseIf CLng(m.Msg) = WM_NCLBUTTONUP Then
      If Me.Opacity <> 1.0 Then Me.Opacity = 1.0
    End If
    ' -- Business as usual
    MyBase.DefWndProc(m)
  End Sub
```

