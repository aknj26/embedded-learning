# LED

## Objective
Turning on an led on STM32NUCLEOF446RE

## Notes (Using HAL Library)
- Changed from 48 to 8Mhz under clock configuration
  
  <img width="177" height="106" alt="image" src="https://github.com/user-attachments/assets/5a6c5eba-4add-45b9-bfb3-57f9afb60a58" />
- PLLCLK selected, HCLK maximized to 180Mhz
  
  <img width="435" height="213" alt="image" src="https://github.com/user-attachments/assets/f5c15b97-01a1-4852-84e8-0f3969cf7eb7" />
- Serial Wire selected under Pinout & Configuration
  
  <img width="515" height="126" alt="image" src="https://github.com/user-attachments/assets/23919221-8e21-4c6b-afb9-d8d595f31ee0" />
- Similarly, for RCC, BYPASS clock source is selected
  
  <img width="517" height="240" alt="image" src="https://github.com/user-attachments/assets/0b684fcb-7a1f-4131-b597-1664a8c840ab" />
- For external led under int main(void) , just before while(1){}
  
  <img width="467" height="23" alt="image" src="https://github.com/user-attachments/assets/3bb56860-3134-4ef7-8627-3c5c5b727078" />
- For LD2 on board
  
  <img width="350" height="17" alt="image" src="https://github.com/user-attachments/assets/cc51938a-169e-4610-b7bc-1fe283e8267c" />
- For external led blinking
  
  <img width="533" height="198" alt="image" src="https://github.com/user-attachments/assets/b5c0dd32-5728-4df4-a048-ad5a451870ff" />
- For internal led blinking
  
  <img width="422" height="142" alt="image" src="https://github.com/user-attachments/assets/5149177d-73b8-413c-a108-dd82f0e95dad" />
  
- Keep in mind the difference between reset and set.
- If external led is connected both will glow.
- PA5 =/= A5
- Can check any in physical connection using 3v3.
- 220Ohms resistor used.
- Nucleo-F446RE has an ST-LINK debugger/programmer built into the board.
- GPIOA = GPIO Port A (stm32 has multiple like A, B, C, etc.)
- GPIO_PIN_5 = Pin number 5 within that port.
- state = GPIO_PIN_SET (high) or GPIO_PIN_RESET (low).
- HAL_GPIO_WritePin(GPIOx, GPIO_PIN_x, state);
- HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5); = Take whatever state PA5 currently has and switch it to the opposite state, thus, state not required (more useful for blinking.)
- HAL_Delay(500); = pause execution for 500ms.
- HAL = Hardware Abstraction Layer (ST provides a library called the STM32 HAL, instead of directly manipulating the STM32's hardware registers yourself.)

## Notes (Register level)
- Register level code to glow an external led for STM32NUCLEOF446RE
- RCC->AHB1ENR = register inside the STM32's RCC peripheral where AHB1 = one of the STM32's internal buses.
- RCC_AHB1ENR_GPIOAEN = Enable the clock to GPIOA because STM32 peripherals are generally clock-gated to save power.
- |= = setting a particular bit without disturbing the other bits.
- GPIOA->MODER = access GPIOA's mode register.
- Every GPIO pin has 2 bits in the MODER register eg. PA0 → bits 0,1
- 00 → Input; 01 → Output; 10 → Alternate Function; 11 → Analog
- <img width="491" height="195" alt="image" src="https://github.com/user-attachments/assets/43ea92a5-3f0a-4135-b53b-9dea848832a4" />
- <img width="408" height="402" alt="image" src="https://github.com/user-attachments/assets/34653381-1ac7-4e40-a9de-3d6ccf39f08e" />
- <img width="375" height="266" alt="image" src="https://github.com/user-attachments/assets/798c88c3-494b-4e01-bf02-7f516bd8ca66" />



## Tutorial link
https://www.youtube.com/watch?v=vKyL43qXPpk&t=1690s

https://www.youtube.com/watch?v=rLtWj2y9niM for led using HAL specifically

## Implementation
Implemented turning an external LED on and blinking, internal led on (LD2 connected to PA5/D13) and it blinking

## Modification
Blinking/Delay
