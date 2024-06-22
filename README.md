Assembly Project Report: RISC-V RV32I Simulator

Farida Islam, Khaled Nana, Janna Osama, and Zeina Elsawy
CSCE2303 Computer Organization and Assembly Language Programming (2024 Spring)
Department of Computer Science and Engineering, AUC












A brief description of your implementation including any bonus features included
The given C++ code functions as a simulator or interpreter for a simplified Instruction Set Architecture (ISA), which includes basic features and structures. It comprises the necessary header files for input/output operations and data structures. The ISA instructions are represented by a 2D array that includes their name, type, opcode, and encoding. Registers are controlled using an integer array that is initialized to zero, and a program counter keeps track of the current instruction. Memory is controlled using two vectors: one for assembly-like commands and the other for data values. Some of the functions we utilized include string search, binary and hexadecimal conversions, and case handling for reading the text file. It lays the framework for implementing the  RISC-V RV32I's simulation or interpretation, which include additional logic for instruction execution, input processing, and output production. Lastly we implemented one bonus feature which was to output all values in decimal, binary, and hexadecimal rather than just decimal which is assumed to be the default.
Any design decisions and/or assumptions you made
We decided on reading from a text file rather than a user input mechanism to improve the efficiency and organization of our code. This option helps create a cleaner, more streamlined system, making it easier to understand and employ. Furthermore, using a text file reader simplifies case processing when compared to user inputs. We used a switch case structure to read the instructions in the text file and execute the appropriate actions. The register file utilizes an integer array of 32 registers, each of which is initialized to zero and accessible by its index. Memory management is supported by two vectors: one for storing assembly-like instructions and another for storing data. 
Any known bugs or issues in your simulator
In our simulator, we had two significant problems. The first issue is about how we handle the "stack" in our code. We realized that it's better to define the "stack" within the specific function where it is used, instead of making it a global variable. This way, we make sure that the "stack" behaves consistently within that function and doesn't accidentally affect other parts of the code. The second problem happens when our simulator reads text files that contain commas. Commas are often used as separators in text files, but they can cause trouble during the parsing process. This means that the instructions or data in the file might not be interpreted correctly. The same issue arises when simulating memory, as commas within data values can lead to errors in how the memory is represented. This can result in unexpected behavior when running the program. To fix this problem, we created a function that removes all commas in the inserted text file.

A list of programs (and associated data if any) you simulated
Our plan to evaluate the implemented ISA involved testing three programs in the simulated environment. First, we'll test a program focusing on basic math operations like addition, subtraction, and multiplication to see how the registers work and how accurate the calculations are. Then, we'll check a program that uses control flow instructions, like loops, to see how well the branching and conditions work. Lastly, we'll try a program that deals with memory-related instructions to make sure data is properly stored and retrieved. It's important to note that our initial attempt to split the text files and commands into three separate files for better readability was unsuccessful. Instead, we implemented a switch case to handle all 44 instructions. 
A user guide showing how to compile and run your simulator including a full simulation example step-by-step with screenshots.
To execute this code, first launch the program. Upon startup, a question will display, requesting that the user provide the name of the text file. It's critical to type the file name accurately, including the ".txt" extension.
The output will then be presented, including each line from the text file and the program counter. This method is repeated for two more text files, as we separated the instructions for better organization.
Finally, the final output shows the program counter's progression and the modifications performed in each register in decimal, 32-bit binary, and hexadecimal forms.
All screenshots will be attached with project file






