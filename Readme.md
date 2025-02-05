# ns3_energy-aware-throttling Project

  

Arquivos utilizados para realização do estudo experimental para o trabalho de mestrado com o objetivo da análise de estratégias de throttling para incremento de disponibilidade em dispositivos IoT dirigidos à energia. 

  

## Table of Contents

  

- [Preparação](#preparação)
- [Execução](#execução)
- [Arquivos](#arquivos-utilizados)


  

## Preparação

  

O simulador [NS-3](https://github.com/nsnam/ns-3-dev-git) foi utilizado como ferramenta de apoio para o experimento, sendo assim, siga preliminarmente as instruções de instalação do simulador [pré-requisitos](https://github.com/nsnam/ns-3-dev-git/blob/master/doc/installation/source/quick-start.rst), disponível no repositório do simulador.  

Uma vez, instalado os pre-requisitos, basta copiar os arquivos deste repositório, configurar o simulador e fazer o build do projeto:

```
./ns3 configure --enable-examples --enable-tests
```
  ```
./ns3 build
```

  > **Note:** É recomendado, acrescentar apenas os [arquivos utilizados](#arquivos) na versão default do simulador substituindo os arquivos necessários. Para eventual consulta, na branch auxiliar todos os arquivos estão disponivéis para consulta, seu uso é desencorajado pois apresenta um build completo para máquina utilizado para a execução do estudo experimental. 

## Execução 

  Após sucesso no build do projeto, os passos a seguir são necessários para execução do experimento:  

 1. Inserir os valores para as variáveis independentes que serão utilizadas editando o arquivo `stratch/exp.py`
	 > As variaveis independentes aceitam uma lista de valores. Tenha em mente que quanto mais valores utilizados mais cenários serão executados. 
 2. Executar o comando `python scratch/exp.py`
 3. Ao fim, os resultados obtidos estarão disponíveis no arquivo `summary.csv`

## Arquivos Utilizados

```
/
├── summary.csv
├── run_all.sh
├── scratch/
│   ├── config.ini
│   ├── DISP1.cc
│   ├── DISP2.cc
│   ├── DISP3.cc
│   ├── DISP4.cc
│   └── exp.py
└── src/
	└── energy/
       ├──  helper/
       │	└──  throttling_strategy.h
       ├── model/
       │	├──  energy-buffer.cc
       │	├──  energy-buffer.h
       │	├──  throttling-fixed-rate.cc
       │	├──  throttling-fixed-rate.h
       │	├──  throttling-energy-based.cc
       │	├──  throttling-energy-based.h
       │	├──  throttling-energy-input-based.cc
       │	└──  throttling-energy-input-based.h
       └  CMakeLists.txt
 ```


