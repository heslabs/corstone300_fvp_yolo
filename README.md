# Corstone-300 FVP Examples

[Arm Virtual Hardware](https://developer.arm.com/Tools%20and%20Software/Arm%20Virtual%20Hardware) (AVH) delivers ready-to-use models of Arm-based processors, systems and third party hardware. Arm Virtual Hardware runs as an application in the cloud to simplify, automate, accelerate and cost-reduce maintenance and development processes. This enables fast prototyping, build and deployment with efficient selection of the best Arm-based silicon for a new or updated application.

---
### Early Software Development using Arm Virtual Hardware
* **Arm Virtual Hardware (AVH)** supports the software development cycle of embedded, IoT, and ML applications and provides essential components for effective integration into Continuous Integration/Continuous Delivery (CI/CD) and MLOps development flows.
* **Fixed Virtual Platforms (FVPs)**
Precise simulation models of Arm Cortex-M based reference platforms, such as Corstone-300/310.
* **AVH Corellium models**
Functionally accurate virtual representations of popular IoT development boards
Cortex-A based systems with Linux OS support, such as Raspberry Pi and NXP i.MX.


---
### Prerequisites
* Linux desktop for Arm tool chain
* Docker environment on Linux desktop

---
<img src="https://github.com/user-attachments/assets/253568f9-d259-4760-b0d0-a43323402aa1" width=600>

---
### Arm Corstone Subsystem

* The Grove Vision V2 is based on Arm Cortex-M55 and Ethos-U55 platform in the Arm Corstone-300 subsystem IP
* Arm Corstone is designed as the foundation for an efficient, high-performance SoC and includes a reference design to efficiently integrate Arm IPs with power, clock, debug, and security infrastructure. 

<img src="https://github.com/user-attachments/assets/525e578d-f26c-46f5-99ab-f1bca6d77d89" width=750>

<img src="https://github.com/user-attachments/assets/065f2b7e-d60e-435c-9a09-f4ba0f13a7f5" width=750>

#### Arm Cortex-M55 Processor 
* Reference: [[Arm Developer Pages]](<https://developer.arm.com/documentation/101051/0101/?lang=en>)
* The Cortex-M55 processor is the first Arm Cortex-M processor supporting the Armv8.1-M architecture. With Arm Helium technology (also known as the M-Profile Vector Extension, MVE).

#### Arm Ethos-U55 NPU [more]
* Reference: [[Arm Developer Pages]](<https://developer.arm.com/Processors/Ethos-U55>)
* The Neural Processing Unit (NPU) improves the inference performance of neural networks. The NPU targets 8-bit and 16-bit integer quantized Convolutional Neural Networks (CNN) and Recurrent Neural Networks (RNN). The NPU supports 8-bit weights.

---
### Arm Ethos-U NPU 
Reference: Arm Ethos-U NPU — Comparison Table Comparison Table [[PDF]](<https://armkeil.blob.core.windows.net/developer/Files/pdf/datasheets/arm-ethos-u-processor-series-product-brief.pdf>)

<img src="https://github.com/user-attachments/assets/3b9837aa-25a4-42c1-abdc-9558b73f1eef" width=550>

---
### Arm IoT Reference Design Platform  
Reference: Arm IoT Reference Design Platform Comparison Table [[PDF]](<https://documentation-service.arm.com/static/6614bbed1bc22b03bca93570?token=>)

<img src="https://github.com/user-attachments/assets/797137ed-3a74-4087-b679-80a5bbe6121c" width=950>
 
