## Development Tool Flow

This guide outlines the workflow for building and running NN models and applications targeting Arm Cortex-M55 + Ethos-U55 on the Corstone-300 Fixed Virtual Platform (FVP) using Docker.

Workflow Summary

1. Build the Docker image
2. Load a pre-built Docker image (optional)
3. Launch the Docker environment
4. Build NN models for M55+U55 (inside Docker)
5. Build application software (inside Docker)
6. Launch the Corstone-300 FVP (inside Docker)


---
### Step 1: Build Docker Image

```
$ cd cs300fvp/YOLOv8_on_WE2/tools
$ docker build -t $(DOCKER_IMAGE) .
```

Alternatively, using the Makefile:
 
```
$ cd cs300fvp/runtime
$ sudo chmod 666 /var/run/docker.sock  # Optional
$ make docker-build
```

---
### Step 2: Load Pre-Built Docker Image (Optional)

```
$ docker image ls
$ docker load --input $(DOCKER_IMAGE_TARFILE)
```

Using the Makefile:
```
$ cd cs300fvp/runtime
$ make docker-load
```

---
### Step 3: Launch Docker Environment

```
$ docker run --rm -it \
         --network=host \
         --env DISPLAY=:1 \
         --privileged \
       -v ${PRJDIR}runtime:/home/ubuntu/YOLOv8_on_WE2/ml-embedded-evaluation-kit/runtime \
          -v /tmp/.X11-unix:/tmp/.X11-unix \
          --volume="/home/demo/.Xauthority:/root/.Xauthority:rw" \
          --workdir /home/ubuntu/YOLOv8_on_WE2/ml-embedded-evaluation-kit/runtime \
                ${DOCKER_IMAGE} bash
```

This command mounts the ${PRJDIR} runtime directory from the host into the Docker container.


---
### Step 4: Build NN models for M55+U55 (inside Docker)
```
$ cd /home/ubuntu/YOLOv8_on_WE2/vela 
$ vela --accelerator-config ethos-u55-64 \
                --config himax_vela.ini \
                --system-config My_Sys_Cfg \
                --memory-mode My_Mem_Mode_Parent \
                --output-dir ./img_yolov8_pose_192 \
                ./img_yolov8_pose_192/yolov8n-pose_full_integer_quant.tflite
```

Output:
```
./img_yolov8_pose_192/yolov8n-pose_full_integer_quant_vela.tflite
```

Or run using Makefile:
```
<docker> $ cd /home/ubuntu/YOLOv8_on_WE2/ml-embedded-evaluation-kit/runtime
<docker> $ make vela
```

---
### Step 5: Build Application Software (inside Docker)

```
$ cd /home/ubuntu/YOLOv8_on_WE2/ml-embedded-evaluation-kit  
$ mkdir -p ./build && cd ./build  
$ cmake ../ -DUSE_CASE_BUILD=img_yolov8_192 \-DETHOS_U_NPU_ENABLED=ON 
$ make -j4
```

Output:
```
<docker> $ cd /home/ubuntu/YOLOv8_on_WE2/ml-embedded-evaluation-kit/runtime
./build/bin/ethos-u-img_yolov8_192.axf
```

Or run using Makefile:
```
<docker> $ make apps
```

---
### Step 6: Launch Corstone-300 FVP (inside Docker)
```
$ cd /home/ubuntu/YOLOv8_on_WE2  
$ ./FVP_Corstone_SSE-300/models/Linux64_GCC-6.4/FVP_Corstone_SSE-300_Ethos-U55 \
                -C ethosu.num_macs=64 \
                ml-embedded-evaluation-kit/runtime/ethos-u-img_yolov8_192.axf
```

Or run using Makefile:
```
<docker> $ cd /home/ubuntu/YOLOv8_on_WE2/ml-embedded-evaluation-kit/runtime
<docker> $ make fvp
```

---
### Expected Test Results

The expected results will be displayed as screen captures showing the output from the FVP simulation. These illustrate successful inference and NN execution on the virtual Corstone-300 platform.


<img src="https://github.com/user-attachments/assets/e6cad153-d7f2-4553-9f8f-37cc33558f58" width=600>

















