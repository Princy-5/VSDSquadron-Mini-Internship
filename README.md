# VSDSquadron-Mini-Internship
Internship at VSD on RISC-V and VLSI using VSDSquadron Mini Board.
### About The Board
* 32-bit RISC-V Core: The heart of the VSDQuadron development board is a powerful 32-bit RISC-V processor. This open-source instruction set architecture (ISA) is known for its flexibility and scalability, making it an excellent choice for educational and development purposes.
* Multiple Clock Options: The board provides various clock configurations, allowing participants to explore different operational frequencies and power modes. This feature is crucial for optimizing performance and energy consumption in embedded applications.
* 15 GPIO Pins: The board is equipped with 15 General Purpose Input/Output (GPIO) pins. These versatile pins can be programmed for various functions, including digital input, digital output, and more. They are essential for interfacing with external sensors, actuators, and other peripherals.
* Software Support: Extensive libraries and frameworks make programming accessible in multiple languages, including C, C++, and Python.
# Task 1 Using a RISC-V simulator, write a C program to count the sum of all numbers from 1 to n.
* Install the RISC-V toolchain using VDI
* Use the Terminal Windows in UBUNTU
* C code for sum of numbers from 1 to N
* Assembly language
1. Virtual box Installed

   <img width="951" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/57126163-6ec6-47d5-86b6-145d8b11db0e">

3. Ubuntu installed

    <img width="923" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/3158286b-672e-40bc-b859-3205d776b0c8">

4. C code to execute The Sum of Numbers 1 to N
      * Leafpad id installed using **sudo snap install leafpad**
      * Create file using **leafpad sum1ton.c &**
      * Here you fnd the leafpad to code **write the code**

         <img width="922" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/463d7ded-79d8-4d05-bb5d-21fc8c3cee70">

5. Output for the C Program
     * Compile the program using **gcc sum1ton.c** then **ls -ltr**
     * Execute the program using **./a.out**
     * The sum for 1 to 5 is 15 which is also verified using calculator

        <img width="802" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/ee24866c-eff6-41fe-ba0b-23c980fdd4bb">
6. C program to RISC-V instruction Set
   * Command 1 **riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c**
   * Switch tab command 2  **riscv64-unknown-elf-objdump -d sum1ton.o| less** and access the main part using main function **/main**
   * To calculate the different execution with Ofast instead of O1 as **riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c**

        <img width="707" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/801f02cb-7972-44e4-89bb-d3a09000c833">
7. search the main() and calculate the RISC-V instruction

    <img width="885" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/975510aa-2a4a-4787-bd07-fbb5f98d0809">

# Conclusion
  By following these steps, you will have a virtual environment set up with the RISC-V toolchain ready for development. This setup allows you to compile and test RISC-V 
  programs, providing a robust environment for RISC-V development projects.


# TASK 2 
# PROJECT 1 - Ticket Terminal Designer: Developing an Automated Parking Ticket Vending Machine
To develop an Automated Parking Ticket Vending Machine using the RISC-V toolchain, we will create a simple program that simulates issuing parking tickets. The program will prompt the user for the number of hours they intend to park, calculate the total cost based on a predefined rate, and print a ticket with the details.
## 1. C PROGRAM CODE
```
#include <stdio.h>
#define RATE_PER_HOUR 5

void print_ticket(int hours, int cost) {
    printf("\n----------------------------\n");
    printf("    Parking Ticket\n");
    printf("----------------------------\n");
    printf("Hours Parked: %d\n", hours);
    printf("Total Cost: $%d\n", cost);
    printf("----------------------------\n");
    printf("Thank you for using our service!\n");
}
int main() {
    int hours;
    int total_cost;

    // Prompt the user for the number of hours they intend to park
    printf("Welcome to the Automated Parking Ticket Vending Machine\n");
    printf("Please enter the number of hours you intend to park: ");
    scanf("%d", &hours);

    // Calculate the total cost
    total_cost = hours * RATE_PER_HOUR;

    // Print the ticket
    print_ticket(hours, total_cost);

    return 0;
}
```

**Steps to Compile and Run the Program**
1. Create the Source File:
     Save the above code in a file named **ticketterminaldesigner.c**
2. Compile the Program:
     Use the RISC-V toolchain to compile the program. Make sure you have the RISC-V toolchain installed and properly set up.

   `
   riscv64-unknown-elf-gcc -o ticketterminaldesigner ticketterminaldesigner.c
   `
3. Run the Program
   To run the program, you need an emulator such as Spike or QEMU. Assuming you have Spike installed, you can run the program as follows:
   `
   spike pk parking_ticket_machine
`
This will prompt you to enter the number of hours, calculate the total cost, and print the parking ticket.

**Behavior: Manages the flow of the program and user interactions**

```
int main() {
    int hours;
    int total_cost;

    // Prompt the user for the number of hours they intend to park
    printf("Welcome to the Automated Parking Ticket Vending Machine\n");
    printf("Please enter the number of hours you intend to park: ");
    scanf("%d", &hours);

    // Calculate the total cost
    total_cost = hours * RATE_PER_HOUR;

    // Print the ticket
    print_ticket(hours, total_cost);

    return 0;
}
```
This code serves as a foundational example of how an automated ticket vending system can be implemented in C. It can be further extended with additional features such as ticket validation, payment processing, and database integration for a more robust solution.
### EXPLANATION OF THE CODE
 * Header Inclusion: The program includes the `stdio.h` header for input/output operations.
 * Rate Definition: The `RATE_PER_HOUR` is defined as a constant value representing the cost per hour of parking.
 * Ticket Printing Function: The `print_ticket` function takes the number of hours and the total cost as arguments and prints the ticket.
 * Main Function:
     * Prompts the user for the number of hours they intend to park.
     * Calculates the total cost by multiplying the hours by the rate.
     * Calls the `print_ticket` function to print the ticket with the details.

This simple program demonstrates the basics of creating an automated ticket vending machine using the RISC-V toolchain.You can expand this program by adding more features such as handling invalid input, offering different parking rates, or integrating with a real hardware interface for a complete system.

<img src="![Screenshot 2024-06-27 140644](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/c99357af-2169-4f72-9b28-d4df107e9262)
">
<img src="![Screenshot 2024-06-27 140736](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/173ebf6f-b430-4e03-8a4e-e923ab7a84ea)
">

## 2. OUTPUT
   * Compile the program using `gcc ticketterminal.c` and execute the program using `./a.out` command
   * Compile the code using the RISC-V GCC compiler with the following command:
     `riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o ticketterminal.o ticketterminal.c`
     
      ![Screenshot 2024-06-27 140736](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/bb554a88-ec7b-417d-ba04-b2b2cf38b175)

      ![Screenshot 2024-06-27 142543](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/20864cfa-5f3c-480c-b84d-257688088326)

   * Now, switch tab to function your main function and calculation using this command :
     `riscv64-unknown-elf-objdump -d ticketterminal.o |less`

     ![Screenshot 2024-06-27 154112](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/118ea750-0ba5-40c4-94a3-cc398881e3b0)
  
   * To access the main function using `/main` statemen

     ![Screenshot 2024-06-27 154317](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/8680c463-9f4c-4489-be04-82d7ea38ec44)

   * Calculation `-o1` instruction then to obtain the difference execute the same function using the -Ofast function like given below
              `riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o ticketterminal.o ticketterminal.c`

        ![Screenshot 2024-06-27 143529](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/22ca5cdb-1c75-4eb3-bb2a-97226dedd0b6)

# CONCLUSION
   This foundational project showcases how RISC-V can be used for practical applications, setting the stage for more complex implementations and integrations with real-world hardware systems. By following these steps, you gain a clear understanding of the development process for embedded systems using the RISC-V architecture.

# TASK 3
# SPIKE simulation and verification with -O1 and -OFast along with running the RISK-V Objdump

   To further validate the functionality and performance of the Automated Parking Ticket Vending Machine program, you can use SPIKE for simulation and verification, and also run the RISC-V `objdump` tool to inspect the compiled binary. Additionally, you can compile the program with different optimization levels (`-O1` and `-Ofast`) to observe the impact on performance and code size.
**Verification with Optimization Levels:**
   * Verify the program's behavior with two different levels of optimization:
   * `-O1`: This optimization level enables basic optimizations that improve performance without significantly increasing compilation time.
   * `ofast`: This level enables aggressive optimizations, potentially breaking strict standards compliance for maximum performance.
## Steps to Compile, Simulate, and Verify with SPIKE
 1. Compile with Different Optimization Levels:
     First, compile the program with the `-O1` optimization level:

    `riscv64-unknown-elf-gcc -O1 -o ticketterminaldesigner ticketterminaldesigner.c`

    Then, compile the program with the `-Ofast` optimization level:

     `riscv64-unknown-elf-gcc -O1 -o ticketterminaldesigner_Ofast ticketterminaldesigner.c`

       ![Screenshot 2024-06-27 201633](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/02098558-a1da-4dbb-820f-7fa67228670e)

 I used an AI tool to generate the initial code for the Automated Parking Ticket Vending Machine. Afterward, I compiled the code using the RISC-V toolchain and employed the SPIKE simulator for debugging and verification. By compiling the code with different optimization levels (`-O1` and `-Ofast`) and using `riscv64-unknown-elf-objdump` to inspect the generated machine code, I ensured the correctness and efficiency of the program.

**(DEBUG done here) command:**

   * `riscv64-unknown-elf-objdump -d ticketterminaldesigner |less`

      ![Screenshot 2024-06-27 154112](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/193546cd-7742-41b8-a020-0c55f5c51e54)

      ![Screenshot 2024-06-27 205915](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/4dec1697-e91c-4095-9776-894ba942d3ed)

2. Spike simulation:
   * Running with spike
     `spike pk ticketterminaldesigner`

     ![Screenshot 2024-06-27 202029](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/a0b558b4-be10-4ddb-8d87-cd9d5438df8d)

3. Generating and Inspecting Objdump:

   * To debug the spike we need this command `spike -d pk ticketterminaldesigner`
   * Then, by using the command `until pc 0 100b0`,which is the 1st line command of the main function the program counter runs from the 0 till the code 100b0
   * To find the contents of the code we need to use the command `reg 0 sp` in which we content of the 100b0 th line
   * To find the content in the next line just give `ENTER`
   * Initially the value of the sp is `0X0000003ffffffb40` then the next step the sp values get subtracted with the hexadecimal and we get `0X0000003ffffffb20`
   * Finally, by subtracting the both main function values we get the 3rd output as `0X000000ffffffb20`

   ![Screenshot 2024-06-27 204120](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/f11eff1d-7078-46bf-b9e7-abbb5e59594e)

   <img width="959" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/d5dbd0de-b806-465a-b0d0-0ec9c6542d6c">

# CONCLUSION
  
  By compiling the Automated Parking Ticket Vending Machine program with different optimization levels, simulating it with SPIKE, and inspecting the generated machine code using objdump, you can gain insights into the performance and efficiency of your code on the RISC-V architecture. This process helps ensure that the program operates correctly and efficiently under different optimization settings, providing a deeper understanding of the compiler's impact on the code.


# TASK 4 
## Identify various RISC-V instruction type (R, I, S, B, U, J) and exact 32-bit instruction code in the instruction type format for below RISC-V instructions
ADD r6, r2, r1

SUB r7, r1, r2

AND r8, r1, r3

OR r9, r2, r5

XOR r10, r1, r4

SLT r11, r2, r4

ADDI r12, r4, 5

SW r3, r1, 2

SRL r16, r14, r2

BNE r0, r1, 20

BEQ r0, r0, 15

LW r13, r1, 2

SLL r15, r1, r2

Upload the 32-bit pattern on Github"

**About RISC-V Instruction Type**

 RISC-V, is an open standard instruction set architecture (ISA), categorizes its instructions into several types based on their formats and intended operations. These primary RISC-V instruction types are:

1. **R-type (Register-type)**:
   - These instructions operate on registers and typically involve arithmetic or logical operations between two source registers, storing the result in a destination register.
   - Example: add rd, rs1, rs2 (Addition)

2. **I-type (Immediate-type)**:
   - These instructions also operate on registers but include an immediate value (constant) as part of the operation. They are used for operations like immediate arithmetic, loads, and conditional branches.
   - Example: addi rd, rs1, imm (Add Immediate)

3. **S-type (Store-type)**:
   - These instructions store a value from a register into memory. They involve specifying a base address (in a register) and an offset to calculate the memory address.
   - Example: sw rs2, offset(rs1) (Store Word)

4. **B-type (Branch-type)**:
   - These instructions perform conditional branches based on comparisons between two registers. They determine whether to jump to a new address based on the result of the comparison.
   - Example: beq rs1, rs2, offset (Branch if Equal)

5. **U-type (Upper Immediate-type)**:
   - These instructions load a large immediate value (shifted left by 12 bits) into a register. They are used to set the upper bits of a register without affecting the lower bits.
   - Example: lui rd, imm (Load Upper Immediate)

6. **J-type (Jump-type)**:
   - These instructions perform unconditional jumps to a new address. They are typically used for procedure calls or long jumps within a program.
   - Example: jal rd, offset (Jump and Link)

Each of these instruction types has a specific format, opcode, and field layout in the instruction encoding, allowing RISC-V processors to efficiently execute a wide range of operations while maintaining simplicity and modularity in the instruction set architecture

 ![git](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/2adc9f5a-4428-418f-b5b2-bfd24d0420cc)


# R-Type Instructions (Register-Register)

R-Type instructions format: `funct7 | rs2 | rs1 | funct3 | rd | opcode`

* ADD r1, r2, r3

    ```Opcode: 0110011
       Funct7: 0000000
       Funct3: 000
       rs1 (r2): 00010 (binary)
       rs2 (r3): 00011 (binary)
       rd (r1): 00001 (binary)
       Instruction Code: 0000000 00011 00010 000 00001 0110011```
* SUB r3, r1, r2
  
   ```Opcode: 0110011
      Funct7: 0100000
      Funct3: 000
      rs1 (r1): 00001 (binary)
      rs2 (r2): 00010 (binary)
      rd (r3): 00011 (binary)
      Instruction Code: 0100000 00010 00001 000 00011 0110011```
* AND r2, r1, r3

   ```Opcode: 0110011
      Funct7: 0000000
      Funct3: 111
      rs1 (r1): 00001 (binary)
      rs2 (r3): 00011 (binary)
      rd (r2): 00010 (binary)
      Instruction Code: 0000000 00011 00001 111 00010 0110011```

* OR r8, r2, r5

  ```Opcode: 0110011
     Funct7: 0000000
     Funct3: 110
     rs1 (r2): 00010 (binary)
     rs2 (r5): 00101 (binary)
     rd (r8): 01000 (binary)
     Instruction Code: 0000000 00101 00010 110 01000 0110011```

* XOR r8, r1, r4
  
  ```Opcode: 0110011
     Funct7: 0000000
     Funct3: 100
     rs1 (r1): 00001 (binary)
     rs2 (r4): 00100 (binary)
     rd (r8): 01000 (binary)
     Instruction Code: 0000000 00100 00001 100 01000 0110011```

* SLT r10, r2, r4
  
  ```Opcode: 0110011
     Funct7: 0000000
     Funct3: 010
     rs1 (r2): 00010 (binary)
     rs2 (r4): 00100 (binary)
     rd (r10): 01010 (binary)
     Instruction Code: 0000000 00100 00010 010 01010 0110011```

 
 # I-Type Instructions (Immediate)

 I-Type instructions format: `imm[11:0] | rs1 | funct3 | rd | opcode`

 - ADDI r12, r3, 5

    ``` Opcode: 0010011
        Funct3: 000
        rs1 (r3): 00011 (binary)
        rd (r12): 01100 (binary)
        Immediate (5): 00000101 (binary)
        Instruction Code: 00000101 00011 01100 000 0010011```

- SW r3, r1, 4

    ``` Opcode: 0100011
        Funct3: 010
        rs1 (r1): 00001 (binary)
        rs2 (r3): 00011 (binary)
        Immediate (4): 000000100 (binary)
        Instruction Code: 000000100 00001 00011 010 0100011```
   
- SRL r16, r11, r2

     ```Opcode: 0110011
        Funct7: 0000000
        Funct3: 101
        rs1 (r11): 01011 (binary)
        rs2 (r2): 00010 (binary)
        rd (r16): 10000 (binary)
        Instruction Code: 0000000 00010 01011 101 10000 0110011```

# S-Type Instructions (Store)

S-Type instructions format: `imm[11:5] | rs2 | rs1 | funct3 | imm[4:0] | opcode`

  - SW r3, r1, 4

       ``` Opcode: 0100011
           Funct3: 010
           rs1 (r1): 00001 (binary)
           rs2 (r3): 00011 (binary)
           Immediate (4): 000000100 (binary)
           Instruction Code: 000000100 00001 00011 010 0100011```

# B-Type Instructions (Branch)

B-Type instructions format: `imm[12|10:5] | rs2 | rs1 | funct3 | imm[4:1|11] | opcode`

- BNE r0, r1, 20
  
   ```Opcode: 1100011
      Funct3: 001
      rs1 (r0): 00000 (binary)
      rs2 (r1): 00001 (binary)
      Immediate (20): 0000101000 (binary)
      Instruction Code: 0000101000 00000 00001 001 1100011```

- BEQ r0, r0, 15
  
  ``` Opcode: 1100011
      Funct3: 000
      rs1 (r0): 00000 (binary)
      rs2 (r0): 00000 (binary)
      Immediate (15): 0000001111 (binary)
      Instruction Code: 0000001111 00000 00000 000 1100011```

# U-Type Instructions (Upper Immediate)

  There are none in the provided list

# J-Type Instructions (Jump)

- LW r13, r11, 2

   ```Opcode: 0000011
     Funct3: 010
     rs1 (r11): 01011 (binary)
     rd (r13): 01101 (binary)
     Immediate (2): 00000000010 (binary)
     Instruction Code: 00000000010 01011 01101 010 0000011```
   
- SLL r15, r11, r2

   ```Opcode: 0110011
     Funct7: 0000000
     Funct3: 001
     rs1 (r11): 01011 (binary)
     rs2 (r2): 00010 (binary)
     rd (r15): 01111 (binary)
     Instruction Code: 0000000 00010 01011 001 01111 0110011```

# Summary

 These instructions and their corresponding formats provide a clear representation of how RISC-V organizes its operations. The exact 32-bit codes ensure that each instruction is properly encoded for execution in a RISC-V processor.


# TASK 5
## RISC-V Core Verilog netlist and Testbench for Functional simulation.
 
### Acknowledgements Section :
 
Referencing a GitHub repository: `https://github.com/vinayrayapati/rv32i/`

I developed a comprehensive set of commands and successfully achieved the desired output for my project. This accomplishment was greatly aided by the invaluable guidance and examples provided by the GitHub repository maintained by Vinay Rayapati (https://github.com/vinayrayapati/rv32i/). The repository served as a crucial reference for understanding the required techniques and applying them effectively in my implementation. I am deeply grateful for the insights and resources offered by this repository, which significantly contributed to the success of my project.

## REFERENCE-DRIVEN DEVELOPMENT

* Clone the Reference Repository

* Set Up Simulation Tools (GTKWave)

* Edit the Testbench File

* Run the Functional Simulation

**WORKFLOW**

1. Cloning the Reference:

   * Cloning is the process of creating a local copy of a remote repository. This allows you to have a complete copy of the repo
   * **Command 1** : git clone `http://github.com/vinayrayapati/rv32i.git my_ticket_rv32i`
   * **Command 2** : cd `my_printterminal_rv32i`

     <img width="959" alt="h" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/0b1a743c-e729-40ed-a417-3bf31836e63f">
     This will download the project into a local directory named my_printterminal_rv32i.

2. Simulation Tools:

* **command 3** : `sudo apt update`

* **command 4** : `sudo apt install inverilog gtkwave`

  <img width="376" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/9fffc5fa-4835-48fb-af4b-97c33e9f5998">
 
  <img width="433" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/93e32656-9095-4c50-8dd3-37d6bc3b1880">

3. Testbench File:

Here we use the Testbench to setup our environment to test and validate code

* Open Testbench file using text editor:

* `nano iiitb_rv32i_tb.v`

  <img width="956" alt="g" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/74e24ded-7287-4937-a9f6-7a86586d0e44">

* Simulation
  
* `iverilog -o rv32i_simulation iiitb_rv32i.v iiitb_rv32i_tb.v`

  <img width="480" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/36418bd8-4f89-40ab-8f7b-35abab2b59da">

4. Run Functional Simulation:

    `vvp rv32i_simulation`

   <img width="959" alt="h" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/901e24d0-28da-497d-9409-3773db46f98f">

* Here we get he Output in the form of a wave

* `gtkwave simulation.vcd`

* Here we get the gtkwave windows and Output can be obtained.

   <img width="920" alt="i" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/ee09be0e-294a-4271-9ddf-b0fef3e0e001">

# OUTPUT

## ADD (r1,r2,r3)

<img width="752" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/a248c596-55a0-4e6b-928f-b604d1d636d9">

## SUB (r3,r1,r2)

<img width="747" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/6c188d96-554e-4314-99f7-a32078f5a6ab">

## AND (r2,r1,r3)

<img width="749" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/e57e6865-594d-4f99-b101-44613f50cd8c">

## OR (r8,r2,r5)

<img width="745" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/76691961-7d36-4d8b-a80b-67f32d27ec9b">

## XOR (r8,r1,r4)

<img width="743" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/452dabf3-0091-4c01-86c2-d1ae5f3d29d9">

##  SLT (r10,r2,r4)

<img width="746" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/4b3b61ef-cde5-4e6f-8a1f-34340858733f">

## BEQ (r0,r0,15)

<img width="743" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/8531ef10-20d4-4246-97f5-3460ad6a4081">

## BNE (r0,r1,20)

<img width="742" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/1932f3e2-faf8-47d8-8487-957dc1047425">

## SLL (r15,r11,r2)

<img width="747" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/7e880df9-bf82-4776-87f9-0443376a6c6d">

## GTKWAVE WINDOW

<img width="843" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/bcb3189b-ddae-4caf-828d-2dea0d383078">


The tests have been completed and all results have been confirmed.


# TASK 6

## Implementation of 2-bit Comparator using VSDSquadron Mini Board

Here's the updated documentation for 2-bit Comparator using VSDSquadron Mini Board

### Overview
This project aims to design and implement a 2-bit comparator using the VSDSquadron Mini board. A 2-bit comparator is a digital circuit that compares two 2-bit binary numbers and indicates whether one number is greater than, less than, or equal to the other. The project involves designing the comparator logic using C programming in Visual Studio Code, setting up the hardware connections on a breadboard, and verifying the functionality through LEDs connected to the output.

**Project Objective**
The objective of this project is to:

* Design a 2-bit comparator using C programming.
* Implement the designed comparator on the VSDSquadron Mini board.
* Verify the correct functionality of the comparator by using LEDs to display the comparison results.
* Gain hands-on experience in digital circuit design, C programming, and hardware implementation.

### Key Components

* VSDSquadron Mini Board : The main microcontroller board used for processing and logic implementation.
* Breadboard and Jumper Wires : For building and testing the circuit.
* LEDs : To display the comparison results.This project requires 3 LEDs.
* Resistors : To limit the current to the LEDs.220Ohm resistors are used in this project.

## Pin Configuration

| LED  |	VSD SQUADRON BOARD|
|------|-------------------|
| LED1 |	PIN4 (PD4)        |
| LED2 |	PIN5 (PD5)        |
| LED3 |	PIN6 (PD6)        |

**Functional Description**

* A > B: LED1 (Yellow color) lights up when a is greater than b.
* A < B: LED2 (Red color) lights up when a is less than b.
* A = B: LED3 (Green color) lights up when both numbers are equal.

Truth Table of 2-bit comparator
|A1|A0|B1|B0|A>B|A=B|A<B|
|--|--|--|--|---|---|---|
|0 |0	|0 |0	|0  |	1 | 0 |
|0 |0 |0 |1 |0	 | 0 | 1 |
|0	|0	|1	|0 |0  |	0 | 1 |
|0 |0 |1 |1	|0	 | 0 | 1 |
|0	|1	|0	|0 |1  |	0 | 0 |
0	1	0	1	0	1	0
0	1	1	0	0	0	1
0	1	1	1	0	0	1
1	0	0	0	1	0	0
1	0	0	1	1	0	0
1	0	1	0	0	1	0
1	0	1	1	0	0	1
1	1	0	0	1	0	0
1	1	0	1	1	0	0
1	1	1	0	1	0	0
1	1	1	1	0	1	0









  
  



  
  








       

 
 














   

 
 









        

     
   










   
      
   
      
     
     
      
      
      
     

       



     







