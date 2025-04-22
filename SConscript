from building import *
import os

cwd = GetCurrentDir()
path = [os.path.join(cwd, 'Inc')]
src_path = os.path.join(cwd, 'Src')
path += [os.path.join(cwd, 'Inc/Legacy')]

CPPDEFINES = ['USE_HAL_DRIVER']

src = [
os.path.join(src_path, 'stm32wlxx_hal.c'),
os.path.join(src_path, 'stm32wlxx_hal_comp.c'),
os.path.join(src_path, 'stm32wlxx_hal_cortex.c'),
os.path.join(src_path, 'stm32wlxx_hal_crc.c'),
os.path.join(src_path, 'stm32wlxx_hal_crc_ex.c'),
os.path.join(src_path, 'stm32wlxx_hal_cryp.c'),
os.path.join(src_path, 'stm32wlxx_hal_cryp_ex.c'),
os.path.join(src_path, 'stm32wlxx_hal_dma.c'),
os.path.join(src_path, 'stm32wlxx_hal_dma_ex.c'),
os.path.join(src_path, 'stm32wlxx_hal_exti.c'),
os.path.join(src_path, 'stm32wlxx_hal_pwr.c'),
os.path.join(src_path, 'stm32wlxx_hal_pwr_ex.c'),
os.path.join(src_path, 'stm32wlxx_hal_rcc.c'),
os.path.join(src_path, 'stm32wlxx_hal_rcc_ex.c'),
os.path.join(src_path, 'stm32wlxx_hal_rng.c'),
os.path.join(src_path, 'stm32wlxx_hal_gpio.c'),
]

if GetDepend(['RT_USING_SERIAL']) or GetDepend(['RT_USING_NANO', 'RT_USING_CONSOLE']):
    src += [os.path.join(src_path, 'stm32wlxx_hal_uart.c')]
    src += [os.path.join(src_path, 'stm32wlxx_hal_uart_ex.c')]
    src += [os.path.join(src_path, 'stm32wlxx_hal_usart.c')]
    src += [os.path.join(src_path, 'stm32wlxx_hal_usart_ex.c')]

if GetDepend(['RT_USING_I2C']):
    src += [os.path.join(src_path, 'stm32wlxx_hal_i2c.c')]
    src += [os.path.join(src_path, 'stm32wlxx_hal_i2c_ex.c')]


if GetDepend(['RT_USING_SPI']):
    src += [os.path.join(src_path, 'stm32wlxx_hal_spi.c')]
    src += [os.path.join(src_path, 'stm32wlxx_hal_spi_ex.c')]

if GetDepend(['RT_USING_HWTIMER']) or GetDepend(['RT_USING_PWM']):
    src += [os.path.join(src_path, 'stm32wlxx_hal_lptim.c')]
    src += [os.path.join(src_path, 'stm32wlxx_hal_tim.c')]
    src += [os.path.join(src_path, 'stm32wlxx_hal_tim_ex.c')]

if GetDepend(['RT_USING_ADC']):
    src += [os.path.join(src_path, 'stm32wlxx_hal_adc.c')]
    src += [os.path.join(src_path, 'stm32wlxx_hal_adc_ex.c')]


if GetDepend(['BSP_USING_ONCHIP_RTC']):
    src += [os.path.join(src_path, 'stm32wlxx_hal_rtc.c')]
    src += [os.path.join(src_path, 'stm32wlxx_hal_rtc_ex.c')]

if GetDepend(['RT_USING_WDT']):
    src += [os.path.join(src_path, 'stm32wlxx_hal_iwdg.c')]
    src += [os.path.join(src_path, 'stm32wlxx_hal_wwdg.c')]

if GetDepend(['RT_USING_PM']):
    src += [os.path.join(src_path, 'stm32wlxx_hal_lptim.c')]

if GetDepend(['BSP_USING_ON_CHIP_FLASH']):
    src += [os.path.join(src_path, 'stm32wlxx_hal_flash.c')]
    src += [os.path.join(src_path, 'stm32wlxx_hal_flash_ex.c')]
    src += [os.path.join(src_path, 'stm32wlxx_hal_flash_ramfunc.c')]

if GetDepend(['BSP_USING_SUBGHZ']):
    src += [os.path.join(src_path, 'stm32wlxx_hal_subghz.c')]


group = DefineGroup('STM32WL-HAL', src, depend = ['PKG_USING_STM32WL_HAL_DRIVER'], CPPPATH = path, CPPDEFINES = CPPDEFINES)

Return('group')
