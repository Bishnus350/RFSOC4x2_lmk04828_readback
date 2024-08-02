# RFSOC4x2_lmk04828_readback
The readback of the LMK clock is done to confirm that the clock file is loaded correctly. I have designed a simple code to read back the clock file. Users can use the "C" compiled file to get readback, without loading the file. You just need to load the file once and then you can have multiple readbacks to check your PLL status. 
- The source code is taken from "https://gitlab.ras.byu.edu/alpaca/i2c-utils"
- I did some of the modifications.
  
- #Unlock
- casper@localhost:/lib/firmware/rfsoc4x2/chip_readback$ sudo ./three_register_readback
- [sudo] password for casper: 
- LMK register readbacks are R386, R387, R392: 0x018200, 0x018300, 0x018810
- LMK04828 readback status raw register R386: 0x018200
- PLL1 LD STAT: UNLOCK
- LMK04828 readback status raw register R387: 0x018300
- LMK04828 readback status raw register R392: 0x018810
 #Lock
-casper@localhost:/lib/firmware/rfsoc4x2/chip_readback$ sudo ./three_register_readback
- LMK register readbacks are R386, R387, R392: 0x018206, 0x018304, 0x018800
- LMK04828 readback status raw register R386: 0x018206
- PLL1 LD STAT: LOCK
- LMK04828 readback status raw register R387: 0x018304
- LMK04828 readback status raw register R392: 0x018800
#Note: 0x18800 register is for PLL locked or unlocked status. 
