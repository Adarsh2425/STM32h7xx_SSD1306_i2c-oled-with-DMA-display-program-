# STM32H7xx SSD1306 I2C OLED with DMA Display Program

This project provides an optimized program to drive an SSD1306 OLED display with an STM32H7 microcontroller via I2C using DMA for fast, efficient screen updates. It includes high-resolution timing via the DWT cycle counter, enabling precise performance measurement, along with graphics functions for displaying text, shapes, and images.

## Features

- **I2C with DMA Support**: Efficient, non-blocking display updates.
- **DWT Timing**: Accurate timing measurements in microseconds.
- **Graphics Library**: Functions for drawing text, shapes, and images.
- **Low CPU Load**: DMA offloads display data handling from the CPU, ideal for resource-limited applications.
- **Adjustable Display Configurations**: Compatible with different power modes for embedded systems.

## Getting Started

### Prerequisites

- **STM32CubeMX**: For configuring STM32H7 peripherals.
- **STM32CubeIDE or Keil uVision**: For coding, compiling, and uploading.
- **SSD1306 OLED Display**: 128x64 or 128x32 display with I2C interface.

### Setup Instructions

1. **Clone Repository**:
   ```bash
   git clone https://github.com/yourusername/STM32h7xx_SSD1306_i2c-oled-with-DMA-display-program.git
   cd STM32h7xx_SSD1306_i2c-oled-with-DMA-display-program
## Hardware Configuration

1. **Connect OLED Display I2C Pins**:  
   - Connect `SDA` and `SCL` pins on the SSD1306 OLED display to the corresponding I2C pins on the STM32H7.
   - Ensure appropriate pull-up resistors are used if needed.
   
2. **Configure I2C with DMA**:  
   - In STM32CubeMX, configure the I2C peripheral to use DMA for efficient data transfer.
   - Set up DMA priority and channel settings as required for the display.

## System Clock Configuration

1. **Set `SystemCoreClock`**:  
   - Configure the system clock to 64 MHz for this project to match the timing and performance requirements.
   
2. **Enable DWT Cycle Counter**:  
   - Initialize the DWT (Data Watchpoint and Trace) cycle counter in `main.c` for high-precision microsecond timing.

3. **Verify `SystemCoreClock`**:  
   - Ensure that the `SystemCoreClock` value in the code aligns with the actual clock configuration to avoid timing inaccuracies.

## File Structure

- **`src/`**: Contains all source code files, including `main.c`, OLED display control functions, and graphics rendering code.
- **`include/`**: Header files for display control, timing utilities, and graphics functions.
- **`doc/`**: Documentation covering project configuration, peripheral settings, and example usage.

## Usage

### Code Structure Overview

1. **DWT Timing Initialization**:  
   - Sets up the DWT counter in `main.c` for microsecond-level precision timing, ideal for measuring function execution times.

2. **DMA with I2C Setup**:  
   - Configures the I2C peripheral to use DMA for non-blocking OLED updates, reducing CPU load.
   
3. **Graphics Functions**:  
   - The library provides functions for drawing text, shapes, and images on the OLED display. These include methods to draw pixels, lines, rectangles, and text with selectable font sizes.

### Example Usage

To display text and measure the time it takes to update the screen using the DWT cycle counter, use the following example code:

