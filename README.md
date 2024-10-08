
# UwpWinForms

This is a really work in progress project that aims to create a reimplementation of .NET Windows Forms in UWP, using WebView2.

Basically the plan is to use *WebView2* as a rendering sandbox to draw the forms and the relative controls. In the backend remains plain WinForms C#, using the same `System.Windows.Forms` namespace, the `form.designer.cs` file, the `form.cs` file and its relatives events.

At the current state "something" works, only with *EnabledVisualStyles* disabled (not yet implemented):

### Partially drawn controls
- Form
- Button
- GroupBox
- Label
- TextBox
- CheckBox
- RadioButton
- MessageBox

### Working properties after performing layout
- Text (Form, Button, Label, TextBox)
- Size (All controls except Form)
- Location (All controls except Form)
- Anchor (All controls)

### Implemented events
- Click (Button, TextBox, Label)
- TextChanged (TextBox)

### Tested events
- Click (Button)
- TextChanged (TextBox)

Windows management is provided by the great JavaScript library jsPanel, with some minor custom edits to better fit the project.
Dialog icons are from KDE/oxygen-icons

It works on Xbox (tested Xbox Series S) but there are some more issues than running on Windows:
- Cursors
- Missing fonts
- Debug must take place with Visual Studio 2019, VS2022 won't work because it's remote debugger it's not installed in the Xbox system. You can still compile with VS2022.

At the current stage the code quality is really low, please don't look at it until further indication if you don't want to have a stroke.
