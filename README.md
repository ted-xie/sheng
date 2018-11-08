# sheng
A small DFA for under 16 states, designed to execute around the 1 cycle per byte level at all times.

This is adapted from a similarly-named engine used in the Hyperscan regular expression matcher (https://github.com/intel/hyperscan) but is presented here as a standalone project for clarity.

# Compilation and execution
To compile 8x unrolled version:
```
make UNROLL=1
```
To compile no runolled version:
```
make
```

To execute sheng testbench:
```
./sheng
```
# Results
With 8x unrolling, the SSE version ("Sheng") can achieve approximately 23% higher throughput than the no-unroll version. The performance difference for the Basic DFA is negligible, less than 1% difference.

| Experiment | Sheng time (s) | BasicDFA time (s) |
|------------|----------------|-------------------|
| No Unroll  | 0.60772        | 2.83512           |
| 8x Unroll  | 0.496846       | 2.8334            |

## Equipment
CPU: AMD Ryzen 7 1700X @ 3.4 GHz
RAM: 16 GB DDR4 @ 3000 MHz
Operating system: Ubuntu 18.04 LTS
