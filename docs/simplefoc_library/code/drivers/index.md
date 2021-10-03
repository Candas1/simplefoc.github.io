---
layout: default
title: Driver code
nav_order: 3
parent: Writing the Code
permalink: /drivers_config
grand_parent: Arduino <span class="simple">Simple<span class="foc">FOC</span>library</span>
has_children: True
has_toc: False
---

# Driver configuration

<div class="width60">
<img src="extras/Images/drv8302.png" style="width:25%;display:inline"><img src="extras/Images/bgc_30.jpg" style="width:25%;display:inline"><img src="extras/Images/l6234.jpg" style="width:25%;display:inline"><img src="extras/Images/l298n.jpg" style="width:25%;display:inline">
</div>

Arduino <span class="simple">Simple<span class="foc">FOC</span>library</span> supports BLDC and stepper motor drivers:

- [BLDC driver <i class="fa fa-external-link"></i>](bldcdriver)
    - **3 PWM signals** ( 3 phase ) - `BLDCDriver3PWM`
    - **6 PWM signals** ( 3 phase ) - `BLDCDriver6PWM`
- [Stepper drivers <i class="fa fa-external-link"></i>](stepperdriver)
    - **4 PWM signals** ( 2 phase )  - `StepperDriver4PWM`
    - **2 PWM signals** ( 2 phase )  - `StepperDriver2PWM`

    
The driver code is written in a way to support as many different drivers out there as possible and in a way to be fully interchangeable. 
These classes can be used as stand-alone classes and they can be used to set certain PWM value to the driver outputs, see example codes in `utils > driver_standalone_test`.


## Driver support per MCU architecture
    
MCU | 2 PWM mode | 4PWM mode | 3 PWM mode | 6 PWM mode | pwm frequency config 
--- | --- |--- |--- |--- |--- 
Arduino (8-bit) | ✔️ | ✔️ | ✔️ | ✔️ | ❌ (32kHz)
Arduino DUE  | ✔️ | ✔️ | ✔️ | ❌ | ✔️
stm32 | ✔️ | ✔️ | ✔️ | ✔️ | ✔️
esp32 | ✔️ | ✔️ | ✔️ | ✔️ | ✔️ 
esp8266 | ✔️ | ✔️ | ✔️ | ❌ | ✔️ 
samd21/51 | ✔️ | ✔️ | ✔️ | ✔️ | ✔️ 
teensy | ✔️ | ✔️ | ✔️ | ❌ | ✔️ 
Raspberry Pi Pico | ✔️ | ✔️ | ✔️ | ✔️ | ✔️ 
Portenta H7 | ✔️ | ✔️ | ✔️ | ❌ | ✔️ 