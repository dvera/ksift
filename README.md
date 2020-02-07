# ksift

## requirements
- yass
- jellyfish2
- littler
- R and packages docopt, readr

## installation
install dependencies (tested on ubuntu xenial)
```bash

# install R and littler
apt-get install -y r-base r-cran-littler

# install yass
wget -O- https://github.com/laurentnoe/yass/archive/1.15_alpha_9.tar.gz | \
tar zx && \
cd yass-1.15_alpha_9 && \
./configure --with-threads && \
make && \
make install && \
cd /root && \
rm -fr yass-1.15_alpha_9

# install jellyfish
wget https://github.com/gmarcais/Jellyfish/releases/download/v2.3.0/jellyfish-linux && \
chmod +x jellyfish-linux && \
cp jellyfish-linux /usr/local/bin/jellyfish

# install docopt
Rscript -e 'install.packages("docopt", repos="https://cran.rstudio.com")'

# install readr
Rscript -e 'install.packages("readr", repos="https://cran.rstudio.com")'
```

```bash
# install ksift
wget https://github.com/dvera/ksift/archive/master.zip && \
unzip master.zip && \
cp ksift-master/k* /usr/local/bin/
```


```bash
wget https://github.com/dvera/ksift/archive/master.zip && \
unzip master.zip
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


