# BLG210 Simple Computer System Design in Proteus

This project was developed for the BLG210 Computer Architecture and Organization course. The aim of the project is to design and simulate a simple computer system using Proteus.

## Project Overview

The system demonstrates the basic components of a computer architecture, including Program Counter, RAM, Data Bus, Address Bus, Registers, Instruction Register, ALU, Clock, and a manual Control Unit.

The designed system reads data from memory or input, transfers the data through the data bus, stores values in registers, performs an arithmetic operation using the ALU, and displays the result on a 7-segment display.

## Main Components

* Clock
* Program Counter
* RAM
* Address Bus
* Data Bus
* Input Buffer
* Instruction Register
* A Register / Accumulator
* B Register
* ALU
* 7-Segment Display
* Manual Control Unit

## Used Integrated Circuits

| Component       | IC / Element        | Purpose                                      |
| --------------- | ------------------- | -------------------------------------------- |
| Program Counter | 74LS161             | Generates RAM address values                 |
| RAM             | 6116 SRAM           | Stores data values                           |
| Input Buffer    | 74LS245             | Transfers input data to the data bus         |
| Registers       | 74LS173             | Stores IR, A Register, and B Register values |
| ALU             | 74LS181             | Performs arithmetic and logic operations     |
| Display         | 7SEG-BCD            | Shows the ALU result                         |
| Control Unit    | LogicState switches | Manually controls system signals             |

## System Architecture

The Program Counter generates the address value for the RAM. The address lines from the PC to RAM form the Address Bus.

The RAM, input buffer, IR, and registers communicate through the shared Data Bus named DBUS0-DBUS7.

In this project, the RAM and data bus are designed as 8-bit, while the ALU and register operation part uses 4-bit data.

## Data Flow

The general data flow of the system is:

```text
PC -> RAM -> Data Bus -> A Register / IR -> B Register -> ALU -> Display
```

Example operation:

```text
A Register = 5
B Register = 3
ALU Result = 5 + 3 = 8
Display = 8
```

## RAM Control Signals

The RAM is controlled using CE, OE, and WE pins.

| Mode     | CE | OE | WE |
| -------- | -- | -- | -- |
| Read     | 0  | 0  | 1  |
| Write    | 0  | 1  | 0  |
| Disabled | 1  | 1  | 1  |

* CE activates or disables the RAM.
* OE allows the RAM to output data to the data bus.
* WE enables writing data into RAM.

## Control Unit

The control unit is implemented manually using LogicState switches. These switches control:

* PC enable and reset
* RAM read/write mode
* Input enable
* IR load
* A Register load
* B Register load
* ALU operation selection

## ALU Operation

The ALU is implemented using the 74LS181 integrated circuit. In the test operation, the ALU performs addition.

Example:

```text
5 + 3 = 8
```

The result is displayed on the 7-segment display.

## Bit Structure

| Part            | Bit Width |
| --------------- | --------- |
| Data Bus        | 8-bit     |
| RAM Data        | 8-bit     |
| Address Bus     | 4-bit     |
| Program Counter | 4-bit     |
| ALU Operation   | 4-bit     |
| Registers       | 4-bit     |

## Project Files

```text
Proteus_Project/
```

Contains the Proteus project and schematic files.

```text
Report/
```

Contains the project report in PDF format.

```text
Screenshots/
```

Contains circuit screenshots and simulation results.

## Software

* Proteus Design Suite
* Proteus 8.17

## Result

The system successfully reads data, transfers it through the data bus, stores it in registers, performs an arithmetic operation using the ALU, and displays the result on a 7-segment display.
