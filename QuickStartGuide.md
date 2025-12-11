# Running YOLOv8 on FVP - Quickstart Guide

* Demo video: https://youtu.be/EGHxdU756Zo

### 1. Remote access to x86 Linux PC
```
$ ssh fvp@122.116.228.96 -X
Password: ******
```

* -X enables X11 forwarding if GUI output is needed.

### 2. Navigate to Project & Check Makefile
```
$ cd ~/labs/cs300fvp && make
```

* Running make without arguments typically lists available build targets.
* Inspect the Makefile if needed:

```
$ less Makefile
```

### 3. Load Prebuilt Docker Image (heswiki/fvp300we2)
```
$ cd ~/labs/cs300fvp
$ docker load --input ../cs300fvp-images/cs300fvp-we2.tar
$ docker images
```

* Confirms that the cs300fvp-we2 image is successfully imported.

### 4. Start the Docker Environment
```
$ cd ~/labs/cs300fvp
$ make docker-env
```

* Launches the prepared container with all WE2/FVP tools installed.

### 5. Run YOLOv8 on the WE2 FVP

```
$ cd ~/YOLOv8_on_WE2/ml-embedded-evaluation-kit/runtime
$ make yolo
```

This command:
* Starts the WE2 FVP model.
* Executes the YOLOv8 application (*.axf) on the FVP.


