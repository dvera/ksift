# ksift

## requirements
- yass
- jellyfish2
- littler
- R and packages docopt, readr

## installation
```bash
wget https://github.com/dvera/ksift/archive/master.zip && unzip master.zip
```

## usage
```
command line arguments:

-o outputFasta    name of output fasta file to put filtered sequences
-t numthreads     number of CPU threads to use, default: 1
-a maxAT          maximum proportion of ATs allowed in a kmer for use in calculating median kmer abundance, default: 0.7
-k klength        length of k(mer) to use, default: 10
-m minMedian      minimum median of top firstK kmer abundances to keep a sequence, default: 5
-s hashSize       jellyfish hash size, default: 100000
-l minLength      minimum length of sequence to consider, default: 1000
-x maxLength      maximum length of sequence to consider, default: 1000000
```

usage example:
```bash
ksift -o output.fa input.fa
```

usage (docker)
```bash
docker run -u $USR -v $PWD:$PWD -w $PWD vera/ksift -o output.fa input.fa
```


