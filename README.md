Xcode fails to debug a static framework's swift code when the app it is linked to does not contain swift.

Repro steps:

1) Open MyProject in Xcode 11.6
2) Build App scheme
3) Set breakpoint inside FW2VC.viewDidAppear (e.g. FW2.swift line 7)
4) Run App on an iOS 13.6 simulator
5) Hit breakpoint
6) po self in debugger

Observe:

```
(lldb) po self
error: <EXPR>:3:1: error: use of unresolved identifier 'self'
self
^~~~
```