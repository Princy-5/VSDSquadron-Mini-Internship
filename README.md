# VSDSquadron-Mini-Internship
Internship at VSD on RISC-V and VLSI using VSDSquadron Mini Board.
### Development Board Featurs
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

2. Ubuntu installed

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
## 1.C PROGRAM CODE
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
# EXPLANATION OF THE CODE
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

# 2.OUTPUT
   * Compile the program using `gcc ticketterminal.c` and execute the program using `./a.out` command
   * Compile the code using the RISC-V GCC compiler with the following command:
     `riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o ticketterminal.o ticketterminal.c`
     <img src="![Screenshot 2024-06-27 142543](https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/20864cfa-5f3c-480c-b84d-257688088326)

   
     <img src="">
     <img src="">
     <img src="">

     
   










   
      
   
      
     
     
      
      
      
     

       



     







