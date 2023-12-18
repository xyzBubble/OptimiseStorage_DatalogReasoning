This repo includes the benchmark data and executable files of the paper '**Optimised Storage for Datalog Reasoning**' that is accepted by the main track of AAAI 2024. The data description is shown below:

- rules

  - This folder contains the program of three benchmarks used in the evaluation. 
  - The programs shown in this folder are also from [this website](https://krr-nas.cs.ox.ac.uk/2021/modular-reasoning/). We used these programs without any modifications.

- facts
  - This folder contains facts of three benchmarks used in the evaluation.
  - DAG and Relations can be used directly without decompressing.
  - For DBpedia, please merge the files first by using the following commands:
    ```
    cd facts/DBpedia
    cat DBpedia_2016-05-split* > DBpedia_2016-05.tar.gz
    ```

- executable

  - This folder contains the executable files of three approaches: standard, TCModule, and multiScheme. The following commands show how to use the executable file to re-produce the evaluation results for DAG-R. 

    ```
    ./EXE_FILE -shell
    init par-complex-nn
    set reason.use-DRed true
    import 'DAG-R.dlog'
    mat
    import 'DAG.bz2'
    mat
    ```

    To re-produce evaluations of other benchmarks, just replace the program file and dataset file names.
