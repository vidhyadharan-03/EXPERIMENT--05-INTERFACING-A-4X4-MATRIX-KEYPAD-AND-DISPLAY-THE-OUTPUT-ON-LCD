# EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD

## Aim: 
To Interface a 4X4 matrix keypad and show the output on 16X2 LCD display to ARM controller , and simulate it in Proteus
## Components required: 
STM32 CUBE IDE, Proteus 8 simulator .
## Theory:

![image](https://github.com/vasanthkumarch/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/36288975/2a4a795e-1674-4329-ae07-3f5e8d5073e2)

4×4 Keypad Module Pin Diagram
 
4x4 Keypad module Pin Diagram
4×4 Keypad module Pin Diagram
Pin Number	Pin Name	Description
1	R1	Taken out from 1st  ROW
2	R2	Taken out from 2nd  ROW
3	R3	Taken out from 3rd  ROW
4	R4	Taken out from 4th  ROW
5	C1	Taken out from 1st  COLUMN
6	C2	Taken out from 2nd COLUMN
7	C3	Taken out from 3rd  COLUMN
8	C4	Taken out from 4th  COLUMN
4×4 Matrix Keypad Module Hardware Overview
These Keypad modules are made of thin, flexible membrane material. The 4 x4 keypad module consists of 16 keys, these Keys are organized in a matrix of rows and columns. All these switches are connected to each other with a conductive trace. Normally there is no connection between rows and columns. When we will press a key, then a row and a column make contact.

## Procedure : 
 ## LCD 16X2 
   16×2 LCD is named so because; it has 16 Columns and 2 Rows. There are a lot of combinations available like,
   8×1, 8×2, 10×2, 16×1, etc. But the most used one is the 16*2 LCD, hence we are using it here.

All the above mentioned LCD display will have 16 Pins and the programming approach is also the same and hence the choice is left to you. 
Below is the Pinout and Pin Description of 16x2 LCD Module:

![image](https://user-images.githubusercontent.com/36288975/233858086-7b1a88a2-f941-475c-86c2-b3bae68bdf7e.png)
![image](https://user-images.githubusercontent.com/36288975/233857710-541ac1c2-786c-4dfc-b7b5-e3a4868a9cb6.png)
![image](https://user-images.githubusercontent.com/36288975/233857733-05df5dbf-1a1e-479e-85bb-8014a39ad878.png)

4-bit and 8-bit Mode of LCD:

The LCD can work in two different modes, namely the 4-bit mode and the 8-bit mode. In 4 bit mode we send the data nibble by nibble, first upper nibble and then lower nibble. For those of you who don’t know what a nibble is: a nibble is a group of four bits, so the lower four bits (D0-D3) of a byte form the lower nibble while the upper four bits (D4-D7) of a byte form the higher nibble. This enables us to send 8 bit data.

Whereas in 8 bit mode we can send the 8-bit data directly in one stroke since we use all the 8 data lines.

 8-bit mode is faster and flawless than 4-bit mode. But the major drawback is that it needs 8 data lines connected to the microcontroller. This will make us run out of I/O pins on our MCU, so 4-bit mode is widely used. No control pins are used to set these modes. 
 LCD Commands:

There are some preset commands instructions in LCD, which we need to send to LCD through some microcontroller. Some important command instructions are given below:

Hex Code

Command to LCD Instruction Register

0F

LCD ON, cursor ON

01

Clear display screen

02

Return home

04

Decrement cursor (shift cursor to left)

06

Increment cursor (shift cursor to right)

05

Shift display right

07

Shift display left

0E

Display ON, cursor blinking

80

Force cursor to beginning of first line

C0

Force cursor to beginning of second line

38

2 lines and 5×7 matrix

83

Cursor line 1 position 3

3C

Activate second line

08

Display OFF, cursor OFF

C1

Jump to second line, position 1

OC

Display ON, cursor OFF

C1

Jump to second line, position 1

C2

Jump to second line, position 2
 
## Procedure:
 
 1. click on STM 32 CUBE IDE, the following screen will appear
  
  ![img-1](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/f181d2b7-21a7-4997-b55b-77aa0487481f)

 2. click on FILE, click on new stm 32 project 
 
 ![2](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/fb77279b-2418-4594-98f4-4e012db825f2)
![3](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/28d89adf-1d48-453f-a1bd-e39d53daa6e8)


3. select the target to be programmed  as shown below and click on next 

![4](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/a94a3f2d-15a1-4179-8dcb-9cb3b0affb06)
![5](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/92bf629c-04c7-4caf-a3f2-89e22a87743e)

4.select the program name 


5. corresponding ioc file will be generated automatically 

![6](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/8eb55d46-ca9f-43a8-9188-6930fdcfbad7)

6.select the appropriate pins as gipo, in or out, USART or required options and configure 
![7](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/d8593162-8dc0-4441-b38a-c699c90ce594)
![8](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/f578482c-c7e4-4153-a767-764bea8c45bf)

7.click on cntrl+S , automaticall C program will be generated 
![9](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/5e98d16a-f7a2-43ff-9991-d42f40a970b3)
![10](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/f1a71afd-6447-4f3d-802d-4ac7b9014c0b)

8. edit the program and as per required 
![11](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/68eb6d52-c5c0-4c44-bfdb-e14cfbc9b155)

9. Add necessary library files of LCD 16x2 , write the program and use project and build  
![12](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/3064627c-6f95-4e81-b845-a28ff37ee8e2)

10. once the project is bulild 
![13](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/62fc4271-f51e-4361-b8d6-b42470149272)

11. click on debug option 
![14](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/0f07086a-ba3a-4d7d-a3d2-1cc2603dacf6)

12.  Creating Proteus project and running the simulation
We are now at the last part of step by step guide on how to simulate STM32 project in Proteus.

13. Create a new Proteus project and place STM32F40xx i.e. the same MCU for which the project was created in STM32Cube IDE. 
14. After creation of the circuit as per requirement as shown below 

![14](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/3bab112e-fd87-444b-bd97-e472f3392247)

15. Double click on the the MCU part to open settings. Next to the Program File option, give full path to the Hex file generated using STM32Cube IDE. Then set the external crystal frequency to 8M (i.e. 8 MHz). Click OK to save the changes.
https://engineeringxpert.com/wp-content/uploads/2022/04/26.png

16. click on debug and simulate using simulation as shown below 
![15](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/d1af88be-c2b7-4945-b903-f198b66c97dd)

## STM 32 CUBE PROGRAM :
```

#include "main.h"
#include <stdbool.h>
#include "lcd.h"
bool col1,col2,col3,col4;

void SystemClock_Config(void);
static void MX_GPIO_Init(void);
void key();
int main(void)
{
  HAL_Init();
  SystemClock_Config();
  MX_GPIO_Init();
  while (1)
  {
	  key();
	  HAL_Delay(1000);
  }
}
void key()
{
	 Lcd_PortType ports[]={GPIOA,GPIOA,GPIOA,GPIOA};
	  Lcd_PinType pins[]={GPIO_PIN_3,GPIO_PIN_2,GPIO_PIN_1,GPIO_PIN_0};
	  Lcd_HandleTypeDef lcd;
	  lcd=Lcd_create(ports,pins,GPIOB,GPIO_PIN_0,GPIOB,GPIO_PIN_1,LCD_4_BIT_MODE);
	HAL_GPIO_WritePin(GPIOC,GPIO_PIN_0,GPIO_PIN_RESET);
	HAL_GPIO_WritePin(GPIOC,GPIO_PIN_1,GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC,GPIO_PIN_2,GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC,GPIO_PIN_3,GPIO_PIN_SET);

	col1=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_4);
	col2=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_5);
	col3=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_6);
	col4=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_7);

	if(!col1)
	{
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd,"Key 7\n");
		col1=1;
	}
	else if(!col2)
	{
		Lcd_cursor(&lcd,0,1);
				Lcd_string(&lcd,"Key 8\n");
				col2=1;
	}
	else if(!col3)
		{
			Lcd_cursor(&lcd,0,1);
					Lcd_string(&lcd,"Key 9\n");
					col3=1;
		}
	else if(!col4)
		{
			Lcd_cursor(&lcd,0,1);
					Lcd_string(&lcd,"Key /\n");
					col4=1;
		}
	HAL_Delay(500);

	HAL_GPIO_WritePin(GPIOC,GPIO_PIN_0,GPIO_PIN_SET);
		HAL_GPIO_WritePin(GPIOC,GPIO_PIN_1,GPIO_PIN_RESET);
		HAL_GPIO_WritePin(GPIOC,GPIO_PIN_2,GPIO_PIN_SET);
		HAL_GPIO_WritePin(GPIOC,GPIO_PIN_3,GPIO_PIN_SET);

		col1=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_4);
		col2=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_5);
		col3=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_6);
		col4=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_7);

		if(!col1)
		{
			Lcd_cursor(&lcd,0,1);
			Lcd_string(&lcd,"Key 4\n");
			col1=1;
		}
		else if(!col2)
		{
			Lcd_cursor(&lcd,0,1);
					Lcd_string(&lcd,"Key 5\n");
					col2=1;
		}
		else if(!col3)
			{
				Lcd_cursor(&lcd,0,1);
						Lcd_string(&lcd,"Key 6\n");
						col3=1;
			}
		else if(!col4)
			{
				Lcd_cursor(&lcd,0,1);
						Lcd_string(&lcd,"Key *\n");
						col4=1;
			}
		HAL_Delay(500);
		HAL_GPIO_WritePin(GPIOC,GPIO_PIN_0,GPIO_PIN_SET);
			HAL_GPIO_WritePin(GPIOC,GPIO_PIN_1,GPIO_PIN_SET);
			HAL_GPIO_WritePin(GPIOC,GPIO_PIN_2,GPIO_PIN_RESET);
			HAL_GPIO_WritePin(GPIOC,GPIO_PIN_3,GPIO_PIN_SET);

			col1=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_4);
			col2=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_5);
			col3=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_6);
			col4=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_7);

			if(!col1)
			{
				Lcd_cursor(&lcd,0,1);
				Lcd_string(&lcd,"Key 1\n");
				col1=1;
			}
			else if(!col2)
			{
				Lcd_cursor(&lcd,0,1);
						Lcd_string(&lcd,"Key 2\n");
						col2=1;
			}
			else if(!col3)
				{
					Lcd_cursor(&lcd,0,1);
							Lcd_string(&lcd,"Key 3\n");
							col3=1;
				}
			else if(!col4)
				{
					Lcd_cursor(&lcd,0,1);
							Lcd_string(&lcd,"Key -\n");
							col4=1;
				}
			HAL_Delay(500);
			HAL_GPIO_WritePin(GPIOC,GPIO_PIN_0,GPIO_PIN_SET);
				HAL_GPIO_WritePin(GPIOC,GPIO_PIN_1,GPIO_PIN_SET);
				HAL_GPIO_WritePin(GPIOC,GPIO_PIN_2,GPIO_PIN_SET);
				HAL_GPIO_WritePin(GPIOC,GPIO_PIN_3,GPIO_PIN_RESET);

				col1=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_4);
				col2=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_5);
				col3=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_6);
				col4=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_7);

				if(!col1)
				{
					Lcd_cursor(&lcd,0,1);
					Lcd_string(&lcd,"Key ON/C\n");
					col1=1;
				}
				else if(!col2)
				{
					Lcd_cursor(&lcd,0,1);
							Lcd_string(&lcd,"Key 0\n");
							col2=1;
				}
				else if(!col3)
					{
						Lcd_cursor(&lcd,0,1);
								Lcd_string(&lcd,"Key =\n");
								col3=1;
					}
				else if(!col4)
					{
						Lcd_cursor(&lcd,0,1);
								Lcd_string(&lcd,"Key +\n");
								col4=1;
					}


				else
				{
					Lcd_cursor(&lcd,0,1);
				Lcd_string(&lcd,"NO KEY PRESSED");
				}
}
void SystemClock_Config(void)
{
  RCC_OscInitTypeDef RCC_OscInitStruct = {0};
  RCC_ClkInitTypeDef RCC_ClkInitStruct = {0};
  __HAL_RCC_PWR_CLK_ENABLE();
  __HAL_PWR_VOLTAGESCALING_CONFIG(PWR_REGULATOR_VOLTAGE_SCALE2);
  
  RCC_OscInitStruct.OscillatorType = RCC_OSCILLATORTYPE_HSI;
  RCC_OscInitStruct.HSIState = RCC_HSI_ON;
  RCC_OscInitStruct.HSICalibrationValue = RCC_HSICALIBRATION_DEFAULT;
  RCC_OscInitStruct.PLL.PLLState = RCC_PLL_NONE;
  if (HAL_RCC_OscConfig(&RCC_OscInitStruct) != HAL_OK)
  {
    Error_Handler();
  }
  
  RCC_ClkInitStruct.ClockType = RCC_CLOCKTYPE_HCLK|RCC_CLOCKTYPE_SYSCLK
                              |RCC_CLOCKTYPE_PCLK1|RCC_CLOCKTYPE_PCLK2;
  RCC_ClkInitStruct.SYSCLKSource = RCC_SYSCLKSOURCE_HSI;
  RCC_ClkInitStruct.AHBCLKDivider = RCC_SYSCLK_DIV1;
  RCC_ClkInitStruct.APB1CLKDivider = RCC_HCLK_DIV1;
  RCC_ClkInitStruct.APB2CLKDivider = RCC_HCLK_DIV1;

  if (HAL_RCC_ClockConfig(&RCC_ClkInitStruct, FLASH_LATENCY_0) != HAL_OK)
  {
    Error_Handler();
  }
}

static void MX_GPIO_Init(void)
{
  GPIO_InitTypeDef GPIO_InitStruct = {0};

  /* GPIO Ports Clock Enable */
  __HAL_RCC_GPIOC_CLK_ENABLE();
  __HAL_RCC_GPIOA_CLK_ENABLE();
  __HAL_RCC_GPIOB_CLK_ENABLE();
  
  HAL_GPIO_WritePin(GPIOC, GPIO_PIN_0|GPIO_PIN_1|GPIO_PIN_2|GPIO_PIN_3, GPIO_PIN_RESET);

  HAL_GPIO_WritePin(GPIOA, GPIO_PIN_0|GPIO_PIN_1|GPIO_PIN_2|GPIO_PIN_3, GPIO_PIN_RESET);

  HAL_GPIO_WritePin(GPIOB, GPIO_PIN_0|GPIO_PIN_1, GPIO_PIN_RESET);

  GPIO_InitStruct.Pin = GPIO_PIN_0|GPIO_PIN_1|GPIO_PIN_2|GPIO_PIN_3;
  GPIO_InitStruct.Mode = GPIO_MODE_OUTPUT_PP;
  GPIO_InitStruct.Pull = GPIO_NOPULL;
  GPIO_InitStruct.Speed = GPIO_SPEED_FREQ_LOW;
  HAL_GPIO_Init(GPIOC, &GPIO_InitStruct);

  GPIO_InitStruct.Pin = GPIO_PIN_0|GPIO_PIN_1|GPIO_PIN_2|GPIO_PIN_3;
  GPIO_InitStruct.Mode = GPIO_MODE_OUTPUT_PP;
  GPIO_InitStruct.Pull = GPIO_NOPULL;
  GPIO_InitStruct.Speed = GPIO_SPEED_FREQ_LOW;
  HAL_GPIO_Init(GPIOA, &GPIO_InitStruct);
  
  GPIO_InitStruct.Pin = GPIO_PIN_4|GPIO_PIN_5|GPIO_PIN_6|GPIO_PIN_7;
  GPIO_InitStruct.Mode = GPIO_MODE_INPUT;
  GPIO_InitStruct.Pull = GPIO_PULLUP;
  HAL_GPIO_Init(GPIOC, &GPIO_InitStruct);

  GPIO_InitStruct.Pin = GPIO_PIN_0|GPIO_PIN_1;
  GPIO_InitStruct.Mode = GPIO_MODE_OUTPUT_PP;
  GPIO_InitStruct.Pull = GPIO_NOPULL;
  GPIO_InitStruct.Speed = GPIO_SPEED_FREQ_LOW;
  HAL_GPIO_Init(GPIOB, &GPIO_InitStruct);

}
void Error_Handler(void)
{
  __disable_irq();
  while (1)
  {
  }
}

#ifdef  USE_FULL_ASSERT
void assert_failed(uint8_t *file, uint32_t line)
{
  
}
#endif /* USE_FULL_ASSERT */
```


## Output screen shots of proteus  :
 ![out1](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/c7bd26f5-4642-4817-8b92-1baef45878e2)

![out2](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/5af4b2f8-52ca-4f6b-bbe9-9c324b67a0fc)



![out3](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/86f6054f-436b-4655-bc5b-ddbf007cba94)


![out4](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/51dd2e0a-826d-4012-a378-811b8cc2cf0d)



 
 ## CIRCUIT DIAGRAM (EXPORT THE GRAPHICS TO PDF AND ADD THE SCREEN SHOT HERE): 
 

 ![lcdexp4_page-0001](https://github.com/vidhyadharan-03/EXPERIMENT--05-INTERFACING-A-4X4-MATRIX-KEYPAD-AND-DISPLAY-THE-OUTPUT-ON-LCD/assets/114286357/48c5cd2b-7755-4482-af4e-9ca6cda7853d)

 
 
## Result :
Interfacing a 4x4 keypad with ARM microcontroller are simulated in proteus and the results are verified.
