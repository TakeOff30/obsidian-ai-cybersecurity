- The final step is linking, where the linker combines one or more object files, along with necessary libraries, to produce a complete executable file. The linker resolves any remaining symbolic references within the object files, connecting function calls to their corresponding implementations, whether they reside in another object file or a library.
    
- Linking can be performed in two primary ways: static linking and dynamic linking.
    
    - **Static Linking:**
        
        - In static linking, all the required library code is directly copied into the executable file during the linking process.
            
        - The resulting executable is self-contained and does not depend on external libraries at runtime. This leads to a larger executable size.
            
    - **Dynamic Linking:**
        
        - In dynamic linking, the executable file contains only references to the external libraries.
            
        - The actual library code is loaded into memory at runtime when the program is executed. This requires the shared libraries to be available on the system.
            
        - Dynamic linking results in smaller executable files and allows multiple programs to share the same library code in memory, but introduces dependencies.
            
    - The output of the linking phase is an [[ELF]] **executable file**, ready to be executed by the operating system.