# Machine Problem
# Coherence Protocols

### Coding
This code provides the implementation of MSI, MESI, and Dragon coherence protocols.
### Report
Configurations:
* Cache size: vary from 256KB, 512KB, 1MB, 2MB while keeping the cache associativity at 8 and block size at 64B.
* Cache associativity: vary from 4‐way, 8‐way, and 16‐way while keeping the cache size at 1MB and block size at 64B. 
* Cache block size: vary from 64B, 128B, and 256B, while keeping the cache size at 1MB and cache associativity at 8 way. 
* Cache policies: write back and write allocate policy, and use LRU replacement policy for all cases.

MSI, MESI and Dragon protocols. For each simulation, run and collect the following statistics:
1. Number of read transactions the cache has received.               
2. Number of read misses the cache has suffered.                      
3. Number of write transactions the cache has received.                    
4. Number of write misses the cache has suffered.                    
5. Total miss rate (rounded to 2 decimals, should use percentage format)   
6. Number of dirty blocks written back to the main memory.
7. Number of cache-to-cache transfers (from the requestor cache perspective, i.e. how many lines this cache has received from other peer caches)
9. Number of interventions (refers to the total number of times that E/M transits to Shared states. Hint: There are two shared states in Dragon. See Chapter 8 for details)
10. Number of invalidations (any State‐>Invalid)               
11. Number of flushes to the main memory.              
12. Number of issued BusRdX transactions. 

**Present your statistics in both tabular format and figures as well. Finally, by comparing the behavior of various statistics, compare the performance with fixed number of processors and explain your observations. You should provide a detailed description with an insightful discussion to earn full credit.** 

## Getting Started

1. In order to “make” your simulator, you need to execute the following command: (You may need to make changes to the Makefile, if you add your own files.)
 ```
make clean; make; make clobber
 ```
2. After making successfully, it should print out the following:
```
----------------------------------------------------------
-----------(SMP_CACHE)-----------
----------------------------------------------------------
Compilation Done ---> nothing else to make :) 

```
3. An executable called “smp_cache” should be created.
4. In order to run your simulator, you need to execute the following command:
```
./smp_cache <cache_size>  <assoc> <block_size> <num_processors> <protocol> <trace_file>
```
#### Where: 
* `smp_cache`: Executable of the SMP simulator generated after making. 
* `cache_size`: Size of each cache in the system (all caches are of the same size)
* `assoc`: Associativity of each cache (all caches are of the same associativity)
* `block_size`:  Block size of each cache line (all caches are of the same block size) 
* `num_processors`: Number of processors in the system (represents how many caches should be instantiated) 
* `protocol`: Coherence protocol to be used (0: MSI, 1:MESI, 2:Dragon) 
* `trace_file`: The input file that has the multi threaded workload trace. 


## Organization
* `code` - base code for the problem
  * `trace`- trace data set
  * `val.v2` - validation data sets for the code
  * `src` - source code resides in this directory
      * `cache.cc`
      * `cache.h`
      * `main.cc`
      * `Makefile` 

