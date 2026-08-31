# LED

## Objective
Turning on an led on STM32F446RE

## Notes
- <img width="177" height="106" alt="image" src="https://github.com/user-attachments/assets/5a6c5eba-4add-45b9-bfb3-57f9afb60a58" /> Changed from 48 to 8Mhz under clock configuration
- <img width="435" height="213" alt="image" src="https://github.com/user-attachments/assets/f5c15b97-01a1-4852-84e8-0f3969cf7eb7" /> PLLCLK selected, HCLK maximized to 180Mhz.
- <img width="515" height="126" alt="image" src="https://github.com/user-attachments/assets/23919221-8e21-4c6b-afb9-d8d595f31ee0" /> Serial Wire selected under Pinout & Configurations.
- <img width="517" height="240" alt="image" src="https://github.com/user-attachments/assets/0b684fcb-7a1f-4131-b597-1664a8c840ab" /> Similarly, for RCC, BYPASS clock source is selected.
- <img width="467" height="23" alt="image" src="https://github.com/user-attachments/assets/3bb56860-3134-4ef7-8627-3c5c5b727078" /> For external led under int main(void) , just before while(1){}.
- <img width="350" height="17" alt="image" src="https://github.com/user-attachments/assets/cc51938a-169e-4610-b7bc-1fe283e8267c" /> For LD2 on board (if external led is connected both will glow).
- <img width="533" height="198" alt="image" src="https://github.com/user-attachments/assets/b5c0dd32-5728-4df4-a048-ad5a451870ff" /> For external led blinking.
- <img width="422" height="142" alt="image" src="https://github.com/user-attachments/assets/5149177d-73b8-413c-a108-dd82f0e95dad" /> For internal led blinking.

## Tutorial link
https://www.youtube.com/watch?v=vKyL43qXPpk&t=1690s
https://www.youtube.com/watch?v=rLtWj2y9niM for led specifically

## Implementation
Implemented turning an external LED on and blinking, internal led on (LD2 connected to PA5/D13) and it blinking

## Modification
Blinking/Delay
