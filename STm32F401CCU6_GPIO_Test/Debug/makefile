################################################################################
# Automatically-generated file. Do not edit!
# Toolchain: GNU Tools for STM32 (12.3.rel1)
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include Drivers/STM32F4xx_HAL_Driver/Src/subdir.mk
-include Core/Startup/subdir.mk
-include Core/Src/subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

OPTIONAL_TOOL_DEPS := \
$(wildcard ../makefile.defs) \
$(wildcard ../makefile.init) \
$(wildcard ../makefile.targets) \


BUILD_ARTIFACT_NAME := STm32F401CCU6_GPIO_Test
BUILD_ARTIFACT_EXTENSION := elf
BUILD_ARTIFACT_PREFIX :=
BUILD_ARTIFACT := $(BUILD_ARTIFACT_PREFIX)$(BUILD_ARTIFACT_NAME)$(if $(BUILD_ARTIFACT_EXTENSION),.$(BUILD_ARTIFACT_EXTENSION),)

# Add inputs and outputs from these tool invocations to the build variables 
EXECUTABLES += \
STm32F401CCU6_GPIO_Test.elf \

MAP_FILES += \
STm32F401CCU6_GPIO_Test.map \

SIZE_OUTPUT += \
default.size.stdout \

OBJDUMP_LIST += \
STm32F401CCU6_GPIO_Test.list \

OBJCOPY_HEX += \
STm32F401CCU6_GPIO_Test.hex \

OBJCOPY_BIN += \
STm32F401CCU6_GPIO_Test.bin \


# All Target
all: main-build

# Main-build Target
main-build: STm32F401CCU6_GPIO_Test.elf secondary-outputs

# Tool invocations
STm32F401CCU6_GPIO_Test.elf STm32F401CCU6_GPIO_Test.map: $(OBJS) $(USER_OBJS) C:\Users\yunusyosaf\Documents\STM32Workspace\STm32F401CCU6_GPIO_Test\STM32F401CCUX_FLASH.ld makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-gcc -o "STm32F401CCU6_GPIO_Test.elf" @"objects.list" $(USER_OBJS) $(LIBS) -mcpu=cortex-m4 -T"C:\Users\yunusyosaf\Documents\STM32Workspace\STm32F401CCU6_GPIO_Test\STM32F401CCUX_FLASH.ld" --specs=nosys.specs -Wl,-Map="STm32F401CCU6_GPIO_Test.map" -Wl,--gc-sections -static --specs=nano.specs -mfpu=fpv4-sp-d16 -mfloat-abi=hard -mthumb -Wl,--start-group -lc -lm -Wl,--end-group
	@echo 'Finished building target: $@'
	@echo ' '

default.size.stdout: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-size  $(EXECUTABLES)
	@echo 'Finished building: $@'
	@echo ' '

STm32F401CCU6_GPIO_Test.list: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objdump -h -S $(EXECUTABLES) > "STm32F401CCU6_GPIO_Test.list"
	@echo 'Finished building: $@'
	@echo ' '

STm32F401CCU6_GPIO_Test.hex: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objcopy  -O ihex $(EXECUTABLES) "STm32F401CCU6_GPIO_Test.hex"
	@echo 'Finished building: $@'
	@echo ' '

STm32F401CCU6_GPIO_Test.bin: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objcopy  -O binary $(EXECUTABLES) "STm32F401CCU6_GPIO_Test.bin"
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) STm32F401CCU6_GPIO_Test.bin STm32F401CCU6_GPIO_Test.elf STm32F401CCU6_GPIO_Test.hex STm32F401CCU6_GPIO_Test.list STm32F401CCU6_GPIO_Test.map default.size.stdout
	-@echo ' '

secondary-outputs: $(SIZE_OUTPUT) $(OBJDUMP_LIST) $(OBJCOPY_HEX) $(OBJCOPY_BIN)

fail-specified-linker-script-missing:
	@echo 'Error: Cannot find the specified linker script. Check the linker settings in the build configuration.'
	@exit 2

warn-no-linker-script-specified:
	@echo 'Warning: No linker script specified. Check the linker settings in the build configuration.'

.PHONY: all clean dependents main-build fail-specified-linker-script-missing warn-no-linker-script-specified

-include ../makefile.targets
