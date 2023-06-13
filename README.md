# rMCMC
A Gibbs sampler for improving the resolution of recombination rate estimates. 

## Input Files

1. Event File (`-i`)

The events file consists of two columns per crossover event:

* start [in basepairs] 
* end [in basepairs]

Typically, there will be one of these file per-chromosome and the files will be stratified by the sex of the crossover event and the positions are determined using the nearest heterozygote locations within the parental haplotypes. 

2. Number of Meioses File (`-nbmeioses`)

This file determines the genetic regions for which to estimate the genetic map 

[start end nmeioses]

These regions can be finer-scale than the regions of that the crossovers are detected in. Consecutive intervals must have the same start as the previous ending coordinate. 

## Output

Specifying the `-o` with a prefix will generate the `<out>-rates.txt` and `<out>-events.txt` which contain posterior estimates of the recombination rates and number of events respectively. 
 

## Input parameters

1. `-m`: number of meioses in total from the dataset
2. `-c`: number of iterations in the MCMC chain
3. `-r`: prior mean of recombination rate (default 1 cM/Mb)
4. `-v`: prior variance at 1 Mb scale (cM^2) (default 5.0 cM^2)
5. `-b`: number of burn-in iterations (default: 33000)
6. `-d`: iterations between sampling for posterior distribution (default: 1000)
7. `-s`: random seed (default: 42)
8. `-h`: HDI region probability (default: 0.95)
9. `-o`: output file prefix ()
