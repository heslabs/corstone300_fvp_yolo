# Demo

### 1. Remote access to x86 LLinux PC
```
ssh demo@@1.169.238.61 -X
Password: ***
```

### 2. Go to the project and check Makefile for available commands
```
cd ~/labs/cs300fvp && make
```

### 3. Load the prebuilt docker images file (heswiki/fvp300we2)
```
cd ~/labs/cs300fvp
docker load --input ../cs300fvp-docker-images/cs300fvp-we2.tar
docker images
```

### 4. Launch Docker environment
```
cd ~/labs/cs300fvp
make docker-env
```

### 5. Launch FVP and run the applicaton codes (*.axf)
```
cd ~/labs/cs300fvp
make yolo
```
