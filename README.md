# Uso-de-QIIME2-para-analisis-de-16S

## Instalación de Miniconda

En nuestro caso, nuestra computadora trabaja con Python 3.8.13, por tanto, descargamos la versión de Miniconda Miniconda3 Linux 64-bit.

```
wget https://repo.anaconda.com/miniconda/Miniconda3-py38_4.12.0-Linux-x86_64.sh
```

## Instalación de QIIME2

* Descargar el programa

```
wget https://data.qiime2.org/distro/core/qiime2-2022.8-py38-linux-conda.yml
```

* Crear el entorno de QIIME2

```
conda env create -n qiime2-2022.8 --file qiime2-2022.8-py38-linux-conda.yml
```

> Esto demorará unos minutos 

* Eliminar archivo de instalación (Opcional) 

```
rm qiime2-2022.8-py38-linux-conda.yml
```

* Activar el ambiente QIIME2

```
conda activate qiime2-2022.8
```

> Para desactivar el entorno, usamos la linea de comandos `conda deactivate`

Se podrá observar en la terminal el cambio del entorno como:

```
(qiime2-2022.8) user@pc:~$
```

* Prueba de instalación 

```
qiime --help
```

Cuyo resultado es: 

```
Usage: qiime [OPTIONS] COMMAND [ARGS]...

  QIIME 2 command-line interface (q2cli)
  --------------------------------------

  To get help with QIIME 2, visit https://qiime2.org.

  To enable tab completion in Bash, run the following command or add it to
  your .bashrc/.bash_profile:

      source tab-qiime

  To enable tab completion in ZSH, run the following commands or add them to
  your .zshrc:

      autoload -Uz compinit && compinit
      autoload bashcompinit && bashcompinit
      source tab-qiime

Options:
  --version   Show the version and exit.
  --help      Show this message and exit.

Commands:
  info                Display information about current deployment.
  tools               Tools for working with QIIME 2 files.
  dev                 Utilities for developers and advanced users.
  alignment           Plugin for generating and manipulating alignments.
  composition         Plugin for compositional data analysis.
  cutadapt            Plugin for removing adapter sequences, primers, and
                      other unwanted sequence from sequence data.
  dada2               Plugin for sequence quality control with DADA2.
  deblur              Plugin for sequence quality control with Deblur.
  demux               Plugin for demultiplexing & viewing sequence quality.
  diversity           Plugin for exploring community diversity.
  diversity-lib       Plugin for computing community diversity.
  emperor             Plugin for ordination plotting with Emperor.
  feature-classifier  Plugin for taxonomic classification.
  feature-table       Plugin for working with sample by feature tables.
  fragment-insertion  Plugin for extending phylogenies.
  gneiss              Plugin for building compositional models.
  longitudinal        Plugin for paired sample and time series analyses.
  metadata            Plugin for working with Metadata.
  phylogeny           Plugin for generating and manipulating phylogenies.
  quality-control     Plugin for quality control of feature and sequence data.
  quality-filter      Plugin for PHRED-based filtering and trimming.
  sample-classifier   Plugin for machine learning prediction of sample
                      metadata.
  taxa                Plugin for working with feature taxonomy annotations.
  vsearch             Plugin for clustering and dereplicating with vsearch
```

## Creando el archivo Manifest.txt 

Para poder trabajar con todos los archivos QIIMe requiere de una archivo de texto, dentro de este archivo se inserta los nombres de las muestra, la ruta absoluta en donde está ubicada la muestra y el sentido o dirección de las lecturas. Todos estos datos separados por comas. 

Ejemplo:

```
sample-id,absolute-filepath,direction
m001,/ruta/absoluta/m001_2022_S22_L001_R1_001.fastq.gz,forward
m001,/ruta/absoluta/m001_2022_S22_L001_R2_001.fastq.gz,reverse
```

> Recordemos 2 cosas: En como terminan los nombres de las muestras (_L001_R1_001) y que la extensión comprimida (fastq.gz) de archivos provenientes de la tecnología Illumina

