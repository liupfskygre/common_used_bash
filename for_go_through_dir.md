## this is a markdown file

**for, dir**

```console
for D in `find . -type d`
do
    //Do whatever you need with D
done
```
**or**

```console
for D in *; do
    if [ -d "${D}" ]; then
        echo "${D}"   # your processing here
    fi
done
```

**or**
```console
for D in *; do [ -d "${D}" ] && my_command; done
```

**or**
```console
for D in */; do my_command; done
```

**The simplest non recursive way is:**
```console
for d in */; do
    echo "$d"
done
```

**example**
*fetch out all metaSPADES results*
*parameters used*
```console
cd ~/A_Wrighton_lab/Wetland_project/Assembler_test/Frogenwetlasoils_JGI/QC_Genome\ Assembly_readme/
for D in */
do
cd ${D}
cd QC\ and\ Genome\ Assembly
grep -e 'JGI assembly of:' *README.txt >> ~/A_Wrighton_lab/Wetland_project/Assembler_test/Frogenwetlasoils_JGI/QC_Genome\ Assembly_readme/metaspades_summary_methods.txt
grep -e 'spades\.py' *README.txt -A1 >> ~/A_Wrighton_lab/Wetland_project/Assembler_test/Frogenwetlasoils_JGI/QC_Genome\ Assembly_readme/metaspades_summary_methods.txt
cd ~/A_Wrighton_lab/Wetland_project/Assembler_test/Frogenwetlasoils_JGI/QC_Genome\ Assembly_readme/
done

```

**contigs or scaffold summary table**
```
for D in */
do
cd ${D}
cd QC\ and\ Genome\ Assembly
grep -e 'JGI assembly of:' *README.txt >> ~/A_Wrighton_lab/Wetland_project/Assembler_test/Frogenwetlasoils_JGI/QC_Genome\ Assembly_readme/metaspades_summary_number.txt
grep -e 'Minimum \tNumber' *README.txt -A16 >> ~/A_Wrighton_lab/Wetland_project/Assembler_test/Frogenwetlasoils_JGI/QC_Genome\ Assembly_readme/metaspades_summary_number.txt
cd ~/A_Wrighton_lab/Wetland_project/Assembler_test/Frogenwetlasoils_JGI/QC_Genome\ Assembly_readme/
done
```

**contigs **
```
for D in */
do
cd ${D}
cd QC\ and\ Genome\ Assembly
grep -e 'JGI assembly of:' *README.txt >> ~/A_Wrighton_lab/Wetland_project/Assembler_test/Frogenwetlasoils_JGI/QC_Genome\ Assembly_readme/metaspades_summary_number.txt
grep -e 'Minimum \tNumber' *README.txt -A16 >> ~/A_Wrighton_lab/Wetland_project/Assembler_test/Frogenwetlasoils_JGI/QC_Genome\ Assembly_readme/metaspades_summary_number.txt
cd ~/A_Wrighton_lab/Wetland_project/Assembler_test/Frogenwetlasoils_JGI/QC_Genome\ Assembly_readme/
done
```

#m50 (a length cutoff), m50/m90 (length where 50% or 90% of reads align to contigs of this length or larger is: 343/NA
#which means, if you want to have more 50% reads bing mapped, you need to include this length of contigs
