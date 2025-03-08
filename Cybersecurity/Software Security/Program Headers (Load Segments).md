An array of structures. Each structure describes a *segment* of the ELF file. 
* Segments are contiguous regions of the ELF file that will be mapped into memory during program execution. 
* Used by the dynamic linker/loader to load the program into memory. 
* Describes memory regions with different access permissions (read, write, execute). 
* Key Information within each header: 
	* `p_type`: Segment type (e.g., loadable segment, dynamic linking information). 
	* `p_flags`: Segment flags (e.g., read, write, execute). 
	* `p_offset`: Offset of the segment in the file. 
	* `p_vaddr`: Virtual address where the segment should be loaded in memory. 
	* `p_paddr`: Physical address (usually not relevant in modern systems). 
	* `p_filesz`: Size of the segment in the file. 
	* `p_memsz`: Size of the segment in memory. 
	* `p_align`: Alignment requirements for the segment. 
* **Common Segment Types:** 
	* `PT_LOAD`: Loadable segment (contains code and data). 
	* `PT_DYNAMIC`: Dynamic linking information. 
	* `PT_INTERP`: Interpreter path (used for dynamically linked executables). 
	* `PT_NOTE`: Auxiliary information. 
	* `PT_GNU_STACK`: Stack executability. 
	
* **Importance:** Crucial for how the program is loaded and executed in memory. Defines the memory map of the process. 
* **Tools:** `readelf -l <file>` (displays program headers). 