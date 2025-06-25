# SOC_PRJ
PROBLEM STATEMENT: Design and Implementation of a CPU-Based Data Communication System with Addressable Module.

This project is a simulation of a simple CPU-based communication system where the CPU talks to memory, I/O devices, and peripherals all using a shared data bus. Each module knows when to respond, thanks to an address decoder that makes sure only the right component is active at a time. It’s designed to be modular, easy to understand, and educational.

THE MAIN MODULES:

1.CPU System- The CPU is the brain of the system. It sends out 16-bit addresses and control signals like read and write. It manages communication on a shared data bus, making sure data only flows when it's supposed to. It also brings everything together by connecting the memory, I/O, and peripheral modules through the address decoder.

2.Address Decoder- This module figures out who should respond to the CPU based on the address.

0x0000–0x3FFF: Memory

0x4000–0x4FFF: I/O

0x5000–0x5FFF: Peripheral Only one module gets activated at a time, preventing signal clashes on the bus.

3.Memory Module- A simple RAM with 4K storage locations. It can read or write data when the CPU asks it to. If it’s not selected, it stays silent by going into a high-impedance state (like being invisible on the bus).

4.I/O Module- Think of this like a keyboard or display. It has a small internal register to hold data. It only responds when it’s asked to, and like the memory, it keeps quiet when not in use.

5.Peripheral Module- This is similar to the I/O module but meant for things like sensors or actuators. It also uses an internal register and only speaks when spoken to.

6.Testbench- To test everything, we’ve got a testbench that acts like a user or software sending commands to the CPU. It creates a clock signal, drives read/write operations, and prints out results. It’s a great way to see how the whole system works together.
