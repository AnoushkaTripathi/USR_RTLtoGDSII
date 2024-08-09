# USR_RTLtoGDSII

![image](https://github.com/user-attachments/assets/44918133-2784-4cfe-90f0-ca5cd3e16552)

## Yosys commands for gate level synthesis using SKY130 process node and PDK
```
read_verilog iiitb_usr.v
synth -top iiitb_usr
dfflibmap -liberty /home/rakshit/iiitb_usr/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
abc -liberty /home/rakshit/iiitb_usr/lib/sky130_fd_sc_hd__tt_025C_1v80.lib -script +strash;scorr;ifraig;retime,{D};strash;dch,-f;map,-M,1,{D}
clean
flatten
# write synthesized design
write_verilog -noattr iiitb_usr_synth.v
stat
```
