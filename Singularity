Bootstrap: docker
From: bioconductor/release_core2:latest

%setup
    mkdir /scratchLocal
    mkdir /pbtech_mounts
    mkdir /pbtech_mounts/softlib001
    mkdir /pbtech_mounts/oelab_store003
    mkdir /athena
    mkdir /cluster001

%post
    mkdir -p /athena
    mkdir -p /scratchLocal
    locale-gen "en_US.UTF-8"
    dpkg-reconfigure locales
    export LANGUAGE="en_US.UTF-8"
    echo 'LANGUAGE="en_US.UTF-8"' >> /etc/default/locale
    echo 'LC_ALL="en_US.UTF-8"' >> /etc/default/locale
    mkdir /share /local-scratch /Software /scratch
    mkdir /scratchLocal
    mkdir /pbtech_mounts
    mkdir /pbtech_mounts/softlib001
    mkdir /pbtech_mounts/oelab_store003
    mkdir /cluster001
    mkdir -p /scratch/data
    mkdir -p /scratch/logs
    chmod -R 777 /scratch
    chmod 777 /tmp
    chmod +t /tmp
    chmod 777 /Software
    apt-get update
    apt-get install -y apt-transport-https build-essential cmake curl libsm6 libxrender1 libfontconfig1 wget vim git unzip python-setuptools ruby bc
    apt-get install -y libcairo2-dev libxt-dev tk8.5
    apt-get install -y r-base r-recommended r-base-dev
    apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 51716619E084DAB9
    echo "deb https://cloud.r-project.org/bin/linux/ubuntu trusty/" >> /etc/apt/sources.list
    apt-get update
    apt-get install -y r-base-dev gdebi-core
    apt-get install -y time
    # Install R, Python, misc. utilities
    apt-get install -y libopenblas-dev libcurl4-openssl-dev libopenmpi-dev openmpi-bin openmpi-common openmpi-doc openssh-client openssh-server libssh-dev libcairo2-dev wget vim git libssl-dev libcurl4-openssl-dev nano git cmake  gfortran g++ curl wget python autoconf bzip2 libtool libtool-bin python-pip python-dev
    # Rsdtudio Server
    wget https://download2.rstudio.org/rstudio-server-1.0.153-amd64.deb
    gdebi rstudio-server-1.0.153-amd64.deb
    echo "All Set!"

%environment
export R_LIBS_USER="/athena/elementolab/scratch/asd2007/singularity/mylibrary"
