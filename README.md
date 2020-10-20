# CMPE_283_Assignment1-intel
Team Members:

Priyanka Devendran- (id:015231411) Contribution: MSR code for controls : Primary Procbased Secondary Procbased

Preeti Parihar -(id: ) Contribution: MSR code for controls: Entry Exit

Prerequisites • A machine capable of running Linux, with VMX virtualization features exposed.

Requirement: To create a Linux kernel module that will query various MSRs to determine virtualization features available in the CPU.

Functionality : • To read various MSRs to ascertain support capabilities/features - Entry / Exit / Procbased / Secondary Procbased / Pinbased controls • For each group of controls above, interpret and output the values read from the MSR to the system via printk(..), including if the value can be set or cleared.

Following are the steps to be followed:

1. Create a new directory named “Assignments_281” mkdir Assignments_281
2. Save the template “Makefile” in the "Assignments_281" directory.
3. Create file cmpe283-1.c
4. We create different functionality to query all the 5 different MSRs in the file cmpe283-1.c
5. All the different structures are created with description and the bit position by referring to SDM.
6. The To detect the VMX capabilities of CPU, the function report capability() will be called with passing the appropriate parameters to print the different   controls. 
7. We build the module by using the command inside the directory  “Assignments_281”  make
8. When we insert the module in the kernel, the module_init marco will be invoked, which will in turn call the function init_module defined in code.  
Command: sudo insmod ./cmpe283-1.ko
9. Once loaded the VMX features must  be logged in the kernel log and this can be checked by using the command:dmesg
10. When we unload the module the rmmod ,module_exit macro will be invoked, which will in turn call the cleanup_module defined in code
Command:  sudo rmsmod ./cmpe283-1.ko
