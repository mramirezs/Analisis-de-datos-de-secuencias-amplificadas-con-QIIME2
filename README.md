# Uso-de-QIIME2-para-analisis-de-16S

# Instalación de QIIME2

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

* Prueba de instalación 

```
qiime --help
```
