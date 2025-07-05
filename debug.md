# Debug


---
#### Xt error: Can't open display: :1

```
Authorization required, but no authorization protocol specified
xterm: Xt error: Can't open display: :1
make: *** [Makefile:58: gui] Error 1
```

#### Solved

```
Access control of X is probably in the way.
Run xhost + (from package x11-xserver-utils) to completely disable access control.
```
