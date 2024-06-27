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

3. C code to execute The Sum of Numbers 1 to N
      * Leafpad id installed using **sudo snap install leafpad**
      * Create file using **leafpad sum1ton.c &**
      * Here you fnd the leafpad to code **write the code**

         <img width="763" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/f6223570-9184-4e2b-8f4b-e39d983be5b5">

4. Output for the C Program
     * Compile the program using **gcc sum1ton.c** then **ls -ltr**
     * Execute the program using **./a.out**
     * The sum for 1 to 5 is 15 which is also verified using calculator

       <img width="802" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/ee24866c-eff6-41fe-ba0b-23c980fdd4bb">
      
5.Compile and run the C code using RISC-V Simulator 
     * command 1 **riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c**
     * Switch tab command 2  **riscv64-unknown-elf-objdump -d sum1ton.o| less ** and access the main part using main function **/main**
     * To calculate the different execution with Ofast instead of O1 as **riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c**
        <img width="707" alt="image" src="https://github.com/Princy-5/VSDSquadron-Mini-Internship/assets/173944414/9ae39c91-c7ce-43d1-bca6-e7d2a59edc52">



     







