Project title: 
Benchmark performance comparison of In-order and Out-of-order CPU using ARM8 system in Gem5 

1) git clone https://github.com/Metabix/Computer-Architecture.git 
   or you can clone the mibench 
   git clone https://github.com/embecosm/mibench.git
2) sudo apt-get install gcc-arm-linux-gnueabi

3) go to the benchmark files and change the gcc to arm-linux-gnueabi-gcc
    for example : 
        from
            gcc -static ${FILE} -O3 -o bitcnts
        to 
            arm-linux-gnueabi-gcc -static ${FILE} -O3 -o bitcnts
            
4) ./build/ARM/gem5.opt -re configs/example/se.py --cpu-type=ArmAtomicSimpleCPU --mem-size=8192MB -c /home/mohit/testbench/bitcnts

5) check gem5/m5out you will find two files simout and simerr

6) for O3CPU 
./build/ARM/gem5.opt -re configs/example/se.py --cpu-type=ArmO3CPU --mem-size=8192MB -c ~/testbench/basicmath/basicmath_small -o  basicmath_small --caches


Output sheet: 
https://docs.google.com/spreadsheets/d/1-G0LA22AryGNLPD-S85atQ2b0xxEIxdHnhFIW_ZTUJw/edit?usp=sharing

#example 
./build/ARM/gem5.opt -re configs/example/se.py --cpu-type=ArmAtomicSimpleCPU --mem-size=8192MB -c /home/mohit/testbench/fft -o '100 64'

output
Global frequency set at 1000000000000 ticks per second
**** REAL SIMULATION ****
RealOut:
36507.457031 	8945.486328 	15062.376953 	-11203.866211 	40957.750000 	-2219.357422 	31474.785156 	23808.796875 	16854.392578 	43468.031250 	4361.948242 	1770.033325 	9601.200195 	14489.538086 	17883.837891 	14982.211914 	-26206.505859 	16294.192383 	60502.277344 	35139.441406 	26610.037109 	34099.238281 	-10220.405273 	-3309.503174 	62550.234375 	-208.161804 	11350.738281 	43348.164062 	11048.123047 	17615.056641 	22741.373047 	23359.175781 	61335.214844 	23359.175781 	22741.373047 	17615.056641 	11048.123047 	43348.164062 	11350.738281 	-208.161804 	62550.234375 	-3309.503174 	-10220.405273 	34099.238281 	26610.037109 	35139.441406 	60502.277344 	16294.192383 	-26206.505859 	14982.211914 	17883.837891 	14489.538086 	9601.200195 	1770.033325 	4361.948242 	43468.031250 	16854.392578 	23808.796875 	31474.785156 	-2219.357422 	40957.750000 	-11203.866211 	15062.376953 	8945.486328 	
ImagOut:
0.000000 	28601.058594 	5913.202148 	13012.550781 	-12535.392578 	17285.699219 	9751.744141 	-6756.925781 	5634.928223 	8341.526367 	6049.953125 	-21564.484375 	23860.087891 	-27961.521484 	3415.927979 	14343.100586 	-15970.745117 	24716.527344 	-8943.796875 	12784.802734 	13358.523438 	26843.832031 	-46129.496094 	7896.113281 	-3916.364746 	28524.500000 	22838.056641 	-38250.343750 	44084.957031 	-360.251068 	16163.680664 	3432.552246 	0.000000 	-3432.552246 	-16163.680664 	360.251068 	-44084.957031 	38250.343750 	-22838.056641 	-28524.500000 	3916.364746 	-7896.113281 	46129.496094 	-26843.832031 	-13358.523438 	-12784.802734 	8943.796875 	-24716.527344 	15970.745117 	-14343.100586 	-3415.927979 	27961.521484 	-23860.087891 	21564.484375 	-6049.953125 	-8341.526367 	-5634.928223 	6756.925781 	-9751.744141 	-17285.699219 	12535.392578 	-13012.550781 	-5913.202148 	-28601.058594 	
Exiting @ tick 9731007000 because exiting with last active thread context



Ref:
https://github.com/ekut-es/mibench
https://github.com/dependablecomputinglab/csi3102-gem5-profiling
http://gemstone.ecs.soton.ac.uk/gemstone-website/gemstone/tutorial-gem5.html
