# LED

## Objective
Turning on an led on STM32F446RE

## Notes
- <img width="177" height="106" alt="image" src="https://github.com/user-attachments/assets/5a6c5eba-4add-45b9-bfb3-57f9afb60a58" /> changed from 48 to 8Mhz under clock configuration
- <img width="435" height="213" alt="image" src="https://github.com/user-attachments/assets/f5c15b97-01a1-4852-84e8-0f3969cf7eb7" /> PLLCLK selected, HCLK maximized to 180Mhz.
- <img width="515" height="126" alt="image" src="https://github.com/user-attachments/assets/23919221-8e21-4c6b-afb9-d8d595f31ee0" /> Serial Wire selected under Pinout & Configurations.
- <img width="517" height="240" alt="image" src="https://github.com/user-attachments/assets/0b684fcb-7a1f-4131-b597-1664a8c840ab" /> Similarly, for RCC, BYPASS clock source is selected.





## Tutorial link
https://www.youtube.com/watch?v=vKyL43qXPpk&t=1690s

## Implementation
Implemented turning an external LED on and blinking, internal led on (LD2 connected to PA5/D13) and it blinking

## Modification
Blinking/Delay
