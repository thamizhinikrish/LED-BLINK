# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---

### 🧭 **Procedure**

1. Open **STM32CubeIDE**.
<img width="641" height="431" alt="image" src="https://github.com/user-attachments/assets/8441bda8-977b-4f6b-9df8-b20f31b0dc47" />


2. Click **File → New STM32 Project**.
  <img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/8ed86696-2d67-4245-8fc7-90a60e5cf9a7" />
<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/c2af0051-8676-47af-949a-4c10a02f6510" />


3. Select the **target microcontroller** or board and click **Next**.
<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/c6869c4d-357e-4922-937a-643aa8eb6278" />


4. Name the project.
   <img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/e3365b94-be8c-4cde-b3bd-5d4bc22a1f08" />


5. The corresponding `.ioc` file will be generated automatically.
 <img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/a4aac0ea-ab1d-4c13-8799-93f277d49c30" />


6. Configure the pins as **GPIO (Input/Output)**, **USART**, etc. as needed.
<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/b77766b3-1ea2-47d1-ab33-51b1b51f2209" />

7. Save the configuration (`Ctrl + S`) – the base C program will be generated automatically.
   <img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/4ba3ea02-c2b5-43ef-87d6-bb9b9baababf" />

8. Edit the generated main program as required.
 <img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/e4d1b171-8092-4051-8400-aa86ec72a64d" />
<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/48b4c4f0-081b-4677-89df-68eaf160d15c" />


9. Click **Project → Build All**.
   

10. Link the **HEX file** using the post-build process.
    <img width="1053" height="465" alt="image" src="https://github.com/user-attachments/assets/478187a0-0ee6-4c50-9cac-c3b5ee18521b" />

11. Click **Debug** and connect the **STM Nucleo Board**.
    <img width="1080" height="608" alt="image" src="https://github.com/user-attachments/assets/f72fff44-6073-4ae4-aa78-0da455df9af1" />

13. Click **Run** to execute the program.
    
---

### 💻 **Program**


```c
#include "main.h"

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON 

CASE 2: LED OFF

---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.
