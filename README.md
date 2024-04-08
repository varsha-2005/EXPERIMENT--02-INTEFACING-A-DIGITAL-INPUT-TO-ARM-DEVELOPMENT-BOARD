# EXPERIMENT--02-INTERFACING-A-DIGITAL-INPUT-TO-ARM-DEVELOPMENT-BOARD
## Aim: To Interface a Digital Input  (userpush button  ) to ARM   development board and write a  program to obtain  the data and flash the led  
## Components required: STM32 CUBE IDE, ARM IOT development board,  STM programmer tool.
## Theory 
The full form of an ARM is an advanced reduced instruction set computer (RISC) machine, and it is a 32-bit processor architecture expanded by ARM holdings. The applications of an ARM processor include several microcontrollers as well as processors. The architecture of an ARM processor was licensed by many corporations for designing ARM processor-based SoC products and CPUs. This allows the corporations to manufacture their products using ARM architecture. Likewise, all main semiconductor companies will make ARM-based SOCs such as Samsung, Atmel, TI etc.

 
  
## Procedure:
 1. click on STM 32 CUBE IDE, the following screen will appear 
 ![image](https://user-images.githubusercontent.com/36288975/226189166-ac10578c-c059-40e7-8b80-9f84f64bf088.png)

 2. click on FILE, click on new stm 32 project 
 ![image](https://user-images.githubusercontent.com/36288975/226189215-2d13ebfb-507f-44fc-b772-02232e97c0e3.png)
![image](https://user-images.githubusercontent.com/36288975/226189230-bf2d90dd-9695-4aaf-b2a6-6d66454e81fc.png)
3. select the target to be programmed  as shown below and click on next 

![image](https://user-images.githubusercontent.com/36288975/226189280-ed5dcf1d-dd8d-43ae-815d-491085f4863b.png)

4.select the program name 
![image](https://user-images.githubusercontent.com/36288975/226189316-09832a30-4d1a-4d4f-b8ad-2dc28f137711.png)


5. corresponding ioc file will be generated automatically 
![image](https://user-images.githubusercontent.com/36288975/226189378-3abbdee2-0df6-470f-a3cd-79c74e3d3ad8.png)

6.select the appropriate pins as gipo, in or out, USART or required options and configure 
![image](https://user-images.githubusercontent.com/36288975/226189403-f7179f1a-3eae-4637-826b-ab4ec35ba1e1.png)
![image](https://user-images.githubusercontent.com/36288975/226189425-2b2414ce-49b3-4b61-a260-c658cb2e4152.png)


7.click on cntrl+S , automaticall C program will be generated 
![image](https://user-images.githubusercontent.com/36288975/226189443-8b43451d-0b14-47e4-a20b-cc09c6ad8458.png)
![image](https://user-images.githubusercontent.com/36288975/226189450-85ffa969-2ffb-4788-81e5-72d60fdda0f1.png)
8. edit the program and as per required 
![image](https://user-images.githubusercontent.com/36288975/226189461-a573e62f-a109-4631-a250-a20925758fe0.png)

9. use project and build all 
![image](https://user-images.githubusercontent.com/36288975/226189554-3f7101ac-3f41-48fc-abc7-480bd6218dec.png)
10. once the project is bulild 
![image](https://user-images.githubusercontent.com/36288975/226189577-c61cc1eb-3990-4968-8aa6-aefffc766b70.png)

11. click on debug option 
![image](https://user-images.githubusercontent.com/36288975/226189625-37daa9a3-62e9-42b5-a5ce-2ac63345905b.png)

12. connect the  ARM board to power supply and usb 


13. check for execution of the output using run option 



## STM 32 CUBE PROGRAM :

developed by:VARSHA G
register number: 212222230166

#include "main.h"
#include "stdbool.h"
bool PUSHBUTTON;
void SystemClock_Config(void);
static void MX_GPIO_Init(void);
int main(void)
{
    HAL_Init();

    SystemClock_Config();

    MX_GPIO_Init();
    while (1)
  {
    	  PUSHBUTTON=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_13);
	  	 	 if(PUSHBUTTON==0)
	  	 	 {
	  	 		 HAL_GPIO_WritePin(GPIOA,GPIO_PIN_5,GPIO_PIN_SET);
	  	 		 HAL_Delay(2000);
	  	 		 HAL_GPIO_WritePin(GPIOA,GPIO_PIN_5,GPIO_PIN_RESET);
	  	 		 HAL_Delay(2000);
	  	 	 }
	  	 	 else
	  	 	 {
	  	 		 HAL_GPIO_WritePin(GPIOA,GPIO_PIN_5,GPIO_PIN_RESET);
	  	 		 HAL_Delay(2000);
	  	 	 }
   
  }

}

## Output  :

 ![WhatsApp Image 2024-04-01 at 11 08 05 AM](https://github.com/VelasiriSreeja/EXPERIMENT--02-INTEFACING-A-DIGITAL-INPUT-TO-ARM-DEVELOPMENT-BOARD/assets/118344328/66c750b7-5a08-469e-9844-33ce80c885c4)

 
 ![WhatsApp Image 2024-04-01 at 11 08 05 AM (1)](https://github.com/VelasiriSreeja/EXPERIMENT--02-INTEFACING-A-DIGITAL-INPUT-TO-ARM-DEVELOPMENT-BOARD/assets/118344328/f1f0cc96-759c-49a9-aeb5-417a9b5a8f35)

 
## Result :
Interfacing a digital Input (Pushbutton ) with ARM microcontroller based IOT development is executed and the results are verified.
