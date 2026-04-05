# Press-to-Glow-STM32F1-Project-
A beginner-friendly STM32 project demonstrating GPIO input and output using the Bluepill (STM32F103C8T6). The LED turns ON when a button is pressed and OFF when released, helping understand basic embedded programming concepts.
#  STM32 GPIO Button LED Control (Bluepill)

##  Overview

This project is a simple and beginner-friendly introduction to STM32 microcontrollers using the Bluepill board (STM32F103C8T6).

The idea is very basic but important:
 When you press a button, an LED turns ON
 When you release the button, the LED turns OFF

Through this small project, you will understand how a microcontroller reads input signals and controls output devices.

This project is developed using **STM32CubeIDE** and programmed using **STM32CubeProgrammer**.

---

##  Objectives

* Understand GPIO input and output
* Learn how to read a button state
* Learn how to control an LED
* Understand pull-down configuration
* Get familiar with STM32 development workflow

---

##  Hardware Required

* STM32F103C8T6 (Bluepill board)
* Push Button (Tactile Switch)
* Connecting wires
* ST-Link Programmer
* Breadboard (optional but recommended)

---

##  Pin Configuration

| Component | Pin  | Mode              |
| --------- | ---- | ----------------- |
| LED       | PC13 | Output            |
| Button    | PA0  | Input (Pull-down) |

---

##  Circuit Connection

###  Button Connection

* One side of button → **3.3V**
* Other side → **PA0**

The button should be placed **across the center gap of the breadboard**.

###  LED Connection

* Onboard LED is already connected to **PC13**

>  Note: The onboard LED is **active LOW**, meaning:
>
> * LOW signal → LED ON
> * HIGH signal → LED OFF

---

##  Code Logic

The program continuously checks the button state inside the infinite loop.

* If button is pressed → LED turns ON
* If button is not pressed → LED turns OFF

### Code Snippet:

```c
if(HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_0) == GPIO_PIN_SET)
{
    HAL_GPIO_WritePin(GPIOC, GPIO_PIN_13, GPIO_PIN_RESET); // LED ON
}
else
{
    HAL_GPIO_WritePin(GPIOC, GPIO_PIN_13, GPIO_PIN_SET); // LED OFF
}
```

---

##  How to Run the Project

### Step 1: Create Project

* Open STM32CubeIDE
* Select STM32F103C8T6
* Configure:

  * PC13 → Output
  * PA0 → Input (Pull-down)

### Step 2: Generate Code

* Generate initialization code
* Write logic inside `while(1)`

### Step 3: Build Project

* Click build button 
* This generates the `.hex` file

---

##  Programming Method (Using STM32CubeProgrammer)

Instead of uploading directly from the IDE, this project uses a separate programming tool.

### Steps:

1. Build the project in STM32CubeIDE
2. Locate `.hex` file:

   ```
   Project_Name/Debug/Project_Name.hex
   ```
3. Open STM32CubeProgrammer
4. Connect ST-Link to your board
5. Load the `.hex` file
6. Click **Download** to flash

---

##  Why Use STM32CubeProgrammer?

* Gives better understanding of real embedded workflow
* Separates coding and flashing process
* Commonly used in industry

---

##  Expected Output

* Button Pressed → LED ON 
* Button Released → LED OFF 

---

##  Key Learnings

* GPIO Input Reading
* GPIO Output Control
* Pull-down resistor concept
* Active LOW logic
* STM32 HAL library basics
* Embedded development workflow

---

##  Future Improvements

* Add software debounce
* Use external interrupt (EXTI)
* Toggle LED instead of hold
* Control multiple LEDs
* Add delay or pattern

---

##  Conclusion

This is a small but very important project for beginners.
It builds a strong foundation for understanding how microcontrollers interact with real-world components.

Once you understand this, you can move on to more advanced topics like interrupts, timers, and communication protocols.

---

##  Author

Swapnali Rathod.

---


