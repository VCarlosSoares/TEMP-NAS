### GUIA DE INSTALAÇÃO NAS 3.3 ###
### OBS.: Todas as aplicações e tamanhos disponíveis na versão 3.3 ###

### DEPENDÊNCIAS ###

sudo apt install git

sudo apt install gfortran

sudo apt install gcc

sudo apt install make

Baixar o Nas no site oficial ou Clonando este Repositório

### CONFIGURAÇÃO ###

cd ./NPB3.3.1/NPB3.3-OMP/config


touch suite.def

cp make.def.template make.def


nano temp.sh

#!/bin/bash

APP=(" " "is" "ep" "cg" "mg" "ft" "bt" "sp" "lu" "dc" "ua") ;

SIZE=(" " "S" "W" "A" "B" "C") ;

for i in $(seq 10) ; do

   for j in $(seq 5) ; do
   
   VAR=${APP[i]}" "${SIZE[j]} ;
     
   echo $VAR >> suite.def ;
     
   done ;
   
done ;


ctrl + o > Enter


chmod +x temp.sh

./temp.sh

rm temp.sh

### INSTALAÇÃO ###

cd ..

make suite
