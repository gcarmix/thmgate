## Official Writeup of THM_Gate Room on TryHackMe
To solve this CTF room it is necessary to reverse the provided firmware.bin

The first difficulty for the reverser is that the processor is an ESP32 from Espressif, it is not an ARM, nor X86, nor MIPS, 
it is based on Xtensa Tensilica with its own instruction set.

Xtensa is not natively supported by Ghidra or IDA, but there are several plugin out there that can be used:

https://github.com/Ebiroll/ghidra-xtensa
https://github.com/Ebiroll/esp32_flash_loader

The first project adds Xtensa processor to Ghidra, the second allows a flash dump to be parsed/analyzed by Ghidra

Once you have your system configured you can go and reverse the firmware

# Question 1,2 and 3
What is the WiFi Access Point SSID?
What is the WiFi Access Point Password?
What is the user name for the login page?

The first three questions are somewhat easy because the answer is hidden in the defined strings,
so even Ghidra/IDA might be overkill for now, check and double check and you'll find the easy solutions

# Question 4
What is the password for the login page?

This last question is somewhat more complicated and requires an understanding of the disassembled code, because
you won't find it anymore
