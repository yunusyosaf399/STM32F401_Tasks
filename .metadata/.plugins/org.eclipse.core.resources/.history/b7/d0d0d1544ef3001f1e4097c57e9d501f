#include "stm32f4xx_hal.h"

// Define the GPIO Pins for LED and Pushbutton
#define LED_PIN GPIO_PIN_5
#define BUTTON_PIN GPIO_PIN_13
#define LED_PORT GPIOA
#define BUTTON_PORT GPIOC

// Function prototypes
void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
  // HAL Initialization
  HAL_Init();

  // Configure the system clock
  SystemClock_Config();

  // Initialize GPIO pins
  MX_GPIO_Init();

  while (1)
  {
    // Read the button state (active low, so when pressed it will be low)
    if (HAL_GPIO_ReadPin(BUTTON_PORT, BUTTON_PIN) == GPIO_PIN_RESET)  // Button pressed
    {
      // Turn on the LED
      HAL_GPIO_WritePin(LED_PORT, LED_PIN, GPIO_PIN_SET);
    }
    else  // Button not pressed
    {
      // Turn off the LED
      HAL_GPIO_WritePin(LED_PORT, LED_PIN, GPIO_PIN_RESET);
    }
  }
}

void SystemClock_Config(void)
{
  // This function configures the system clock, generated automatically by STM32CubeMX.
  // You can configure this based on the specific clock source you're using.
  // It's usually auto-generated for the STM32F401 in STM32CubeMX.
}

static void MX_GPIO_Init(void)
{
  GPIO_InitTypeDef GPIO_InitStruct = {0};

  // Enable GPIO Ports Clock (A and C in this case)
  __HAL_RCC_GPIOA_CLK_ENABLE();
  __HAL_RCC_GPIOC_CLK_ENABLE();

  // Configure LED Pin as output
  GPIO_InitStruct.Pin = LED_PIN;
  GPIO_InitStruct.Mode = GPIO_MODE_OUTPUT_PP;   // Push-pull mode
  GPIO_InitStruct.Pull = GPIO_NOPULL;            // No internal pull-up/pull-down resistors
  GPIO_InitStruct.Speed = GPIO_SPEED_FREQ_LOW;   // Low speed
  HAL_GPIO_Init(LED_PORT, &GPIO_InitStruct);

  // Configure Pushbutton Pin as input with pull-up resistor
  GPIO_InitStruct.Pin = BUTTON_PIN;
  GPIO_InitStruct.Mode = GPIO_MODE_INPUT;        // Input mode
  GPIO_InitStruct.Pull = GPIO_PULLUP;            // Enable internal pull-up resistor (button is active-low)
  HAL_GPIO_Init(BUTTON_PORT, &GPIO_InitStruct);
}

