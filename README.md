# Calculators For 2HDM
Tools to use SusHi and 2HDMC to compute H/A/h cross section and branching fractions. 

    # In a CMSSW release
    git clone -o upstream git@github.com:cp3-llbb/Calculators42HDM.git cp3_llbb/Calculators42HDM
    module load /nfs/soft/modules/lhapdf/6.1
    export SCRAM_ARCH=slc6_amd64_gcc493
    scram b
    cmsenv

##First, installation of 2HDMC

    cd cp3_llbb/Calculators42HDM
    wget http://www.hepforge.org/archive/2hdmc/2HDMC-1.7.0.tar.gz
    tar -zxvf 2HDMC-1.7.0.tar.gz
    cd 2HDMC-1.7.0
    make
    cd ..

##Second, SusHi installation :

    wget http://www.hepforge.org/archive/sushi/SusHi-1.5.0.tar.gz
    tar -zxvf SusHi-1.5.0.tar.gz
    cd SusHi-1.5.0
    ./configure

Edit the makefile, to link the proper 2HDMC version (1.7.0 in the line 2HDMCPATH = ../2HDMC-1.6.3)

    make predef=2HDMC
    cd ..


## Run the test
    
    python example/test.py

