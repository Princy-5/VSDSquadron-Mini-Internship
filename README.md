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
# Identify various RISC-V instruction type (R, I, S, B, U, J) and exact 32-bit instruction code in the instruction type format for below RISC-V instructions
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





   

 
 









        

     
   










   
      
   
      
     
     
      
      
      
     

       



     







