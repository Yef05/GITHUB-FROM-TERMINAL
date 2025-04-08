# PARCIAL 1 BIOINFORMATICA






## Lista de codigos
### Punto 1 - concatenar secuencias 
* ```cat *.fasta > secuenciasconcat.fasta```

Uso ```cat```, y el asteristo para seleccionar los dos archivos ya que ambos tienen la extensión .fasta. con ```>```  le doy un nombre al nuevo archivo. 

### Punto 1 - cambiar el nombre a las secuencias 
* ```sed -E 's/^(>[^[:space:]]+)[[:space:]]+([[:alnum:]]+)[[:space:]]+([[:alnum:]]+).+/\1_\2_\3/' secuenciasconcat.fasta > seqconcat.fasta```

Con ```-E``` indico que voy a usar expresiones regulares. Con ```^(>[^[:space:]]+)``` indico el comienzo de las secuencias y selecciono el código de las secuencias. Con ``` [[:space:]]+ ``` selecciono los espacios, no uso parentesis porque no los quiero incluir luego. Con ```([[:alnum:]]+)``` selecciono las partes del nombre científico del individuo. 

### Punto 1 - BLAST
* ```salloc```
* ```module load blast/2.7.1```
* ``` makeblastdb -in seqconcat.fasta -dbtype nucl -parse_seqids -out misticetos -title "misticetos"```
* ``` blastn -query query.fasta -task megablast -db trans_gasteracantha -outfmt 7 -word_size 7 -out blast_mistecetos -num_threads 1```
![Resultado del BLAST](https://github.com/Yef05/GITHUB-FROM-TERMINAL/blob/main/blast.png)

