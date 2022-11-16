How to run :
  The make file is already run with arm-linux-gnueabi-gcc

Open Terminal:
  1) Go to Gem5
      cd gem5
  2) Next run the executable 
    ./build/ARM/gem5.opt -re configs/example/se.py --cpu-type=ArmAtomicSimpleCPU --mem-size=8192MB -c ~/testbench/qsort/qsort_large -o  ~/testbench/qsort/input_large
