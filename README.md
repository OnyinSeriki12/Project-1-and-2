    7  # 1. Print your name
    8  echo  ‘’Sarah Onyinoiyi Seriki’’
    9  # 2. Create a folder titled your name
   10  mkdir -p "Sarah_Onyinoiyi_Seriki"
   11  # 3. Create another new directory titled biocomputing and change to that directory with one line of command
   12  mkdir -p biocomputing && cd biocomputing
   13  # 4. Download the 3 files
   14  wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.fna
   15  wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk
   16  wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk -O wildtype2.gbk
   17  # 5. Move the .fna file to the folder titled your name
   18  mv wildtype.fna ../Sarah_Onyinoiyi_Seriki/
   19  # 6. Delete the duplicate gbk file
   20  rm wildtype2.gbk
   21  history
   22  pwd
   23  # 1. Print your name
   24  echo "My name is Sarah Onyinoiyi Seriki"
   25  
   26  # 2. Create a folder titled your name
   27  mkdir -p "Sarah_Onyinoiyi_Seriki"
   28  # 3. Create another new directory titled biocomputing and change to that directory with one line of command
   29  mkdir -p biocomputing && cd biocomputing
   30  # 4. Download the 3 files
   31  wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.fna
   32  wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk
   33  wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk -O wildtype2.gbk
   34  # 5. Move the .fna file to the folder titled your name
   35  mv wildtype.fna ../Sarah_Onyinoiyi_Seriki/
   36  # 6. Delete the duplicate gbk file
   37  rm wildtype2.gbk
   38  # 7. Confirm if the .fna file is mutant or wild type (tatatata vs tata)
   39  echo "Checking if sequence is mutant or wild type..."
   40  if grep -q "tatatata" ../Sarah_Onyinoiyi_Seriki/wildtype.fna; then     echo "Mutant sequence found!"
   41      grep "tatatata" ../Sarah_Onyinoiyi_Seriki/wildtype.fna > ../Sarah_Onyinoiyi_Seriki/mutant_lines.txt; else     echo "Wild type sequence"; fi
   42  # 9. Count number of lines (excluding header) in the .gbk file
   43  echo "Number of sequence lines (excluding header):"
   44  grep -v "^LOCUS" wildtype.gbk | wc -l
   45  # 10. Print the sequence length of the .gbk file (from LOCUS tag)
   46  echo "Sequence length from LOCUS line:"
   47  grep "^LOCUS" wildtype.gbk | awk '{print $3, $4}'
   48  # 11. Print the source organism of the .gbk file (from SOURCE tag)
   49  echo "Source organism:"
   50  grep -m 1 "SOURCE" wildtype.gbk | sed 's/  */ /g'
   51  # 12. List all the gene names in the .gbk file
   52  echo "Gene names in .gbk file:"
   53  grep "/gene=" wildtype.gbk
   54  # 13. Clear your terminal space and print all commands used today
   55  clear
   56  echo "Commands history for today:"
   57  history
   58  # 14. List the files in the two folders
   59  echo "Files in biocomputing folder:"
   60  ls
   61  echo "Files in Sarah_Onyinoiyi_Seriki folder:"
   62  ls ../Sarah_Onyinoiyi_Seriki
   63  history
   64  echo "Step 9: Number of sequence lines (excluding header):"
   65  grep -v "^LOCUS" wildtype.gbk | wc -l
   66  Step 9: Number of sequence lines (excluding header):
   67  12345 
   68  ls
   69  rm 
   70  rm biocomputing
   71  rm biocomputing.txt
   72  rm -r biocomputing 
   73  rm README-cloudshell.txt 
   74  rm -r Sarah_Onyinoiyi_Seriki 
   75  pwd
   76  # 1. Print your name
   77  echo  ‘’Sarah Onyinoiyi Seriki’’
   78  # 2. Create a folder titled your name
   79  mkdir -p "Sarah_Onyinoiyi_Seriki"
   80  # 3. Create another new directory titled biocomputing and change to that directory with one line of command
   81  mkdir -p biocomputing && cd biocomputing
   82  # 4. Download the 3 files
   83  wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.fna
   84  wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk
   85  wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk -O wildtype2.gbk
   86  # 5. Move the .fna file to the folder titled your name
   87  mv wildtype.fna ../Sarah_Onyinoiyi_Seriki/
   88  # 6. Delete the duplicate gbk file
   89  rm wildtype2.gbk
   90  # 7. Confirm if the .fna file is mutant or wild type (tatatata vs tata)
   91  echo "Checking if sequence is mutant or wild type..."
   92  if grep -q "tatatata" ../Sarah_Onyinoiyi_Seriki/wildtype.fna; then     echo "Mutant sequence found!"; else     echo "Wild type sequence"; fi 
   93  # 7 & 8. Confirm if the .fna file is mutant or wild type (tatatata vs tata)
   94  echo "Checking if sequence is mutant or wild type..."
   95  if grep -q "tatatata" ../Sarah_Onyinoiyi_Seriki/wildtype.fna; then     echo "Mutant sequence found!"
   96      grep "tatatata" ../Sarah_Onyinoiyi_Seriki/wildtype.fna > ../Sarah_Onyinoiyi_Seriki/mutant_lines.txt; else     echo "Wild type sequence"; fi 
   97  # 9. Count number of lines (excluding header) in the .gbk file
   98  echo "Number of sequence lines (excluding header):"
   99  grep -v "^LOCUS" wildtype.gbk | wc -l 
  100  # 10. Print the sequence length of the .gbk file (from LOCUS tag)
  101  echo "Sequence length from LOCUS line:"
  102  grep "^LOCUS" wildtype.gbk | awk '{print $3, $4}' 
  103  # 11. Print the source organism of the .gbk file (from SOURCE tag)
  104  echo "Source organism:"
  105  grep -m 1 "SOURCE" wildtype.gbk | sed 's/  */ /g' 
  106  # 12. List all the gene names in the .gbk file
  107  echo "Gene names in .gbk file:"
  108  grep "/gene=" wildtype.gbk 
  109  # 13. Clear your terminal space and print all commands used today
  110  clear
  111  echo "Commands history for today:"
  112  history 
  113  # 14. List the files in the two folders
  114  echo "Files in biocomputing folder:"
  115  ls
  116  echo "Files in Sarah_Onyinoiyi_Seriki folder:"
  117  ls ../Sarah_Onyinoiyi_Seriki 
  118  #End of project 1
  119  # 1. Activate your base conda environment
  120  conda activate base
  121  pwd
  122  source ~/anaconda3/etc/profile.d/conda.sh
  123  conda activate base
  124  pwd
  125  # 1. Download and install Miniconda (if conda is not found)
  126  wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O miniconda.sh
  127  bash miniconda.sh -b -p $HOME/miniconda 
  128  # 2. Initialize conda
  129  eval "$($HOME/miniconda/bin/conda shell.bash hook)" 
  130  # 3. Activate base environment
  131  conda activate base 
  132  # 2. Create a conda environment named funtools
  133  conda create -n funtools python=3.9 -y
  134  conda tos accept --override-channels --channel https://repo.anaconda.com/pkgs/main
  135  conda tos accept --override-channels --channel https://repo.anaconda.com/pkgs/r
  136  conda create -n funtools python=3.9 -y
  137  conda activate funtools
  138  (funtools) serikionyi@cloudshell:~$
  139  conda install -c conda-forge figlet -y
  140  sudo apt-get update && sudo apt-get install -y figlet
  141  figlet "Sarah Onyinoiyi Seriki"
  142  conda install -c bioconda blast -y
  143  conda install -c bioconda samtools -y
  144  conda install -c bioconda bedtools -y
  145  conda install -c bioconda spades -y
  146  conda install -c bioconda bcftools -y
  147  conda install -c conda-forge openblas -y
  148  # Make sure you're in the funtools environment
  149  conda activate funtools  
  150  # Install fastp from bioconda
  151  conda install -c bioconda fastp -y
  152  fastp --version
  153  # Make sure you're in the funtools environment
  154  conda activate funtools  
  155  # Install MultiQC from bioconda
  156  conda install -c bioconda multiqc -y
  157  df -h
  158  conda clean -a -y
  159  conda env list
  160  conda clean -a -y
  161  #The end of project 2 , no space i could not download the last one 

https://github.com/OnyinSeriki12/Project-1-and-2/edit/main/README.md

https://www.linkedin.com/posts/sarah-onyinoyi-seriki-627247266_bioinformatics-hackbio-learningjourney-ugcPost-7368259598627094530-IBke?utm_source=share&utm_medium=member_android
