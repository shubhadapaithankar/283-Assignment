# Steps to complete CMPE 283 - Assignment 1 :

## I created VM on Google Cloud :

1. Create GCP account and setup billing.
2. Install git and fork this repository 
3. In GCP, go to VM instances under compute engine present in the left menu.
4. Create a new VM instance, with the below specifications

       * a. Series : N2
       
       * b. Machine type : n2-standard
       
       * c.Boot disk : Operating system : Ubuntu
                      Version : x86/64, amd64 jammy
                      disk : SSD persistent disk
                      size : 100GB
                      
       * d. Allow Firewall 
5. Select "Equivalent command line" and copy the code required to create a VM instance from CLI
6. Paste this code GCP CLI and add --enable-nested-virtualization --zone=us-central-1a to the code.
<img width="1194" alt="Screen Shot 2022-11-23 at 3 47 12 PM" src="https://user-images.githubusercontent.com/99461999/203664805-fa709db0-4426-48c1-bf2d-a512869e5f4f.png">

<img width="1196" alt="Screen Shot 2022-11-23 at 3 38 41 PM" src="https://user-images.githubusercontent.com/99461999/203664557-eeb58baf-090a-4f1f-903d-ef824accfaaa.png">

7. New VM instance will be opened in a new window
8. This cmpe283-1.c file in the repository includes :

              * Primary Process based controls (IA32_VMX_PROCBASED_CTLS) 
              * Secondary process based controls (IA32_VMX_PROCBASED_CTLS2)
              * Exit controls (IA32_VMX_EXIT_CTLS) 
              * Entry controls (IA32_VMX_ENTRY_CTLS) 
              * Cannot include tertiary controls as it has Can set=No in primary controls 
9. Now, clone the git repository forked in step2, in the vm instance created in GCP
10. Enter into the folder with cd foldername 
11. install gcc and make using `sudo apt install gcc make`
12. install `sudo apt-get linux-headers-$(uname -r)`
13. Now, run `make`command
14. If it is successfully executed, cmpe283-1.ko kernel object file is generated
15. Run command to insert .ko file `insmod ./cmpe283-1.ko`
16. excecute the `dmesg` command  to view the output as below


<img width="814" alt="Screen Shot 2022-11-23 at 4 03 08 PM" src="https://user-images.githubusercontent.com/99461999/203666135-c4949748-376d-4702-a82e-38983cdc9f90.png">


<img width="879" alt="Screen Shot 2022-11-23 at 4 04 23 PM" src="https://user-images.githubusercontent.com/99461999/203666265-e267e9dd-f53d-4ef2-a5cc-a80494cbb63c.png">



