# Apple II SRAM, ditching DRAM modules for a modern, static RAM 
As can be seen in another project, my own built Apple II computer has my first computer-project, at the time i didn't foresee - that the DRAM
modules i bought - they could spoil anytime soon as being decades old (just imagine these capacitors inside leaking charge) - so i naively soldered them
to the DRAM board. Luckly they worked fine at the first, in 2021; 2 years later i tried to load games again, and it didn't work, just throwing a beep with ERROR... at the
first i thought - oh maybe its the TSR cassete cable, then i try swapping the cables! thinking cables were spoiled, then trying find a mono cable instead stereo etc., just at the end, when i ran a memory test that is included somewhere in Apple II ROM code i understood these chips were no longer reliable...

The command for memory check was:

CALL -151

C050 C053 C054 C057 N 265:FF N 266<265.BFFEM 266<265.BFFEV 265:0 N 266<265.BFFEM 266<265.BFFEV 34:14 

So the year before i built a IBM PC XT from scratch with a CGA Card, and i decided to use SRAM instead of DRAM chips, so i thought that this was the next step for the Apple II.
I used a AS6C4008-55PCN SRAM.

As this Apple II was built from scratch - and it needed wider traces to avoid possible transfer errors - the DRAM memory was put aside in a board. So switching to SRAM was simpler, just remaking a board. As DRAM signals RAS and CAS are set with the matrix lower and higher address, this RAS first address must be latched, to produce a full address along CAS0, CAS1, CAS2. AS SRAM has a Databus-In and Databus-Out i to not expose Databus-Out. 



So its technically possible to scrap all the DRAM chips from an original Apple II (!) and put a SRAM chip (!) in the middle but maybe is not okay.
