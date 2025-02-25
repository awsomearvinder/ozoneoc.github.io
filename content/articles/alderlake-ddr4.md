---
title: Alderlake DDR4 Memory Overclocking
---

These notes are for memory overclocking Samsung B-Die on chips such as the 12700K or 12900K; higher end unlocked Alderlake chips with better IMCs.

This is **not** a guide on how to overclock memory, it's only notes exclusive to Alderlake as it can be trickier than normal. If you want to learn how to OC memory, read the [MemTestHelper DDR4 OC Guide](https://github.com/integralfx/MemTestHelper/blob/oc-guide/DDR4%20OC%20Guide.md) by by integralfx.



# Hardware

##### CPU
- Good CPUs for memory overclocking consist of the 12700K, 12900K, and 12900KS. Avoid the 12600K as it is a bottom binned unlocked Alderlake chip, and does not have a very strong IMC most of the time. Also absolutely do not get any locked Alderlake chip, since not only the core is locked, but the SA is locked to `0.95v`, making it hard for you to memory overclock any further than XMP.

##### Motherboard
- For DDR4 OC on Z690, the best value board is the MSI PRO Z690-A DDR4 as it is good value and OCs memory well. Make sure to use the latest BIOS as it improves memory OC significantly (v17.0). Another thing is that the RTLs on that board can tend to be annoying, but nevertheless it is a good board.
- A better board is the ASUS STRIX Z690-A, which costs a lot more than the MSI PRO-A, but it OCs memory a bit better, but is mainly recommended for very experienced overclockes.

##### Memory
- Memory is a little bit more tricky to find, since you will mostly need to look at used deals for Samsung B-Die. Aim to get dual rank 2x16GB kits as it will perform better, but it depends on the price for it to be worth it, as 2x8GB kits can be a lot more common. If you need 32GB but cannot find any good priced 2x16GB kits, then 4x8GB is a viable option, just bare in mind that it won't OC as well as the other two options.


# Notes

##### Alderlake's IMC
- Alderlake's DDR4 IMC is similar to Rocketlake's but slightly better in G1 but worse in G2, which isn't very good compared to Cometlake
- A tight `4000MHz G1` OC on 2x8/2x16 is considered as pretty good as it is quite a lot harder to push further than that

##### Memory Stress Testing Software
- [Alderlake Memory Testing Kit](https://mega.nz/folder/681HEQaB#OkkwsXxzZgCabkco9KUWxA)
  - ycruncher: Run 4 iterations before your TM5 run as it is good at picking out the errors on Alderlake that Extreme1 doesn't
  - TM5 with Extreme1 config by anta777: Run 3 cycles of every OC you do, doing 6-9 cycles on your final OC
  - Prime95 Large FFT: This is very good at testing if your IMC is unstable rather than your memory OC, such as too high or low of an SA voltage

##### Timing Software
- [AsRock Timing Configurator v4.0.13](https://drive.google.com/file/d/11A2CCcXbvAFLVNHPVP9EtZ4hwmsn2yFt/edit)
  - Most reliable on Alderlake
- [MSI Dragon Ball](https://drive.google.com/file/d/1XmKv13D0MgC9fPaA91535wCe9ztoeaHV/view?usp=sharing)
  - Tends to miss/be inaccurate with the RTLs, also do not use this software to change the timings

##### CPU Settings
- E-Cores must be kept on and CPU Ring Ratio set to `33x` in order to achieve the best memory OC possible, since memory should be OC'd before the CPU

##### SA/VDDQ Voltages
- SA should first be set to `1.32` if using 2x8GB, or `1.35v` if using 2x16GB/4x8GB, as the higher memory ranks puts more load on the IMC, there requiring more SA voltage
- VDDQ is complicated and should be left at `1.35v`

##### Command Rate
- `1T` can give a noticable performace uplift and should always be aimed for

##### tREFI
- Alderlake is able to have a higher tREFI than previous generations as it can reach around `262K`, but gets too thermally sensitive past `65535` and should be kept that way for daily OCs, so should be set to `65534` or `65535` depending on the board

##### RTLs
- RTLs should be close together, since being far apart can sometimes indicate instability
- Some boards aren't great at RTL training as it takes a few tries to get them to train properly

##### RTTs
- RTTs should be at `80/60/80` for 2x8GB, or `80/60/120` for 4x8GB/2x16GB

# Special Thanks

Special thanks to users \_L_, ReZ, Mobama, Seby and QXE for helping.
