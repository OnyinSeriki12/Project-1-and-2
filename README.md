 4  # Task 1: Print your name
    5  echo "OnyiSeriki"
    6  # Task 2: Create a folder titled your name
    7  mkdir -p OnyiSeriki
    8  # Task 3: Create another new directory titled biocomputing and change to that directory
    9  mkdir -p biocomputing && cd biocomputing
   10  wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.fna
   11  https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk
   12  https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk 
   13  # Task 5: Move the .fna file to the folder titled your name
   14  mv wildtype.fna ../OnyiSeriki/
   15  # Task 6: Delete the duplicate gbk file
   16  rm wildtype_duplicate.gbk
   17  # Task 7: Confirm if the .fna file is mutant or wild type
   18  echo "Task 7: Checking if .fna file is mutant or wild type"
   19  cd ../OnyiSeriki
   20  if grep -q "tatatata" wildtype.fna; then     echo "✓ File contains MUTANT sequence (tatatata)";     file_type="mutant"; else     echo "✓ File contains WILD TYPE sequence (tata)";     file_type="wildtype"; fi
   21  echo
   22  # Task 8: If mutant, print all matching lines into a new file
   23  echo "Task 8: Processing mutant sequences if present"
   24  if [ "$file_type" = "mutant" ]; then     grep "tatatata" wildtype.fna > mutant_sequences.txt;     echo "✓ Mutant sequences saved to mutant_sequences.txt";     echo "Number of mutant lines found: $(wc -l < mutant_sequences.txt)"; else           echo "✓ No mutant sequences found - file is wild type"; fi
   25  echo
   26  # Change back to biocomputing directory for gbk file analysis
   27  cd ../biocomputing
   28  # Task 9: Count number of lines (excluding header) in the .gbk file
   29  echo "Task 9: Counting lines in .gbk file (excluding header)"
   30  total_lines=$(wc -l < wildtype.gbk)
   31  lines_excluding_header=$((total_lines - 1))
   32  echo "✓ Total lines in wildtype.gbk: $total_lines"
   33  echo "✓ Lines excluding header: $lines_excluding_header"
   34  echo
   35  # Task 10: Print the sequence length of the .gbk file
   36  echo "Task 10: Getting sequence length from LOCUS tag"
   37  sequence_length=$(head -1 wildtype.gbk | awk '{print $3}')
   38  echo "✓ Sequence length: $sequence_length bp"
   39  echo
   40  # Task 11: Print the source organism of the .gbk file
   41  echo "Task 11: Getting source organism"
   42  source_organism=$(grep "^SOURCE" wildtype.gbk | sed 's/SOURCE *//')
   43  echo "✓ Source organism: $source_organism"
   44  echo
   45  # Task 12: List all the gene names of the .gbk file
   46  echo "Task 12: Listing all gene names"
   47  echo "Gene names found:"
   48  grep '/gene=' wildtype.gbk | sed 's/.*\/gene="\([^"]*\)".*/\1/' | sort | uniq | nl
   49  gene_count=$(grep '/gene=' wildtype.gbk | sed 's/.*\/gene="\([^"]*\)".*/\1/' | sort | uniq | wc -l)
   50  echo "✓ Total unique genes found: $gene_count"
   51  echo
   52  # Task 13: Clear terminal and print all commands used today
   53  echo "Task 13: Clearing terminal and showing command history"
   54  echo "Commands used in this session:"
   55  echo "================================="
   56  history | tail -20
   57  echo
   58  # Task 14: List the files in the two folders
   59  echo "Task 14: Listing files in both folders"
   60  echo
   61  echo "Files in OnyiSeriki folder:"
   62  echo "=========================="
   63  ls -la ../OnyiSeriki/
   64  echo
   65  echo "Files in biocomputing folder:"
   66  echo "============================="
   67  ls -la ./
   68  echo
   69  echo "=== Script completed successfully! ==="
   70  echo "Summary:"
   71  echo "- Name printed: OnyiSeriki"
   72  echo "- Folders created: OnyiSeriki, biocomputing"
   73  echo "- Files downloaded and processed"
   74  echo "- Sequence analysis completed"
   75  echo "- File type determined: $file_type"
   76  echo "- Sequence length: $sequence_length bp"
   77  echo "- Source organism: $source_organism"
   78  echo "- Total genes found: $gene_count"
   79  # End of project one
   80  #!/bin/bash
   81  # Bioinformatics Environment Setup Script
   82  # Author: OnyiSeriki
   83  # Description: Sets up a conda environment with essential bioinformatics tools
   84  set -e  # Exit on any error
   85  echo "=================================================="
   86  echo "    Bioinformatics Environment Setup Script"
   87  echo "    Author: OnyiSeriki"
   88  echo "=================================================="
   89  echo
   90  # Function to print colored output
   91  print_status() {     echo -e "\033[32m[INFO]\033[0m $1"; }
   92  print_error() {     echo -e "\033[31m[ERROR]\033[0m $1"; }
   93  print_warning() {     echo -e "\033[33m[WARNING]\033[0m $1"; }
   94  # Check if conda is installed
   95  if ! command -v conda &> /dev/null; then     print_error "Conda is not installed or not in PATH";     exit 1; fi
   96  print_status "Step 1: Activating base conda environment..."
   97  source $(conda info --base)/etc/profile.d/conda.sh
   98  conda activate base
   99  print_status "Base environment activated ✓"
  100  echo
  101  print_status "Step 2: Creating conda environment named 'funtools'..."
  102  if conda env list | grep -q "^funtools "; then     print_warning "Environment 'funtools' already exists. Removing and recreating...";     conda env remove -n funtools -y; fi
  103  conda create -n funtools -y python=3.9
  104  print_status "Environment 'funtools' created ✓"
  105  echo
-get available";     exit 1; fi
  113  echo
  114  print_status "Step 5: Running figlet with your name..."
  115  figlet "OnyiSeriki"
  116  echo
  117  print_status "Adding bioconda channel if not already present..."
  118  conda config --add channels defaults
  119  conda config --add channels bioconda
  120  conda config --add channels conda-forge
  121  conda config --set channel_priority strict
  122  print_status "Bioconda channel configured ✓"
  123  echo
  124  # Array of bioinformatics tools to install
  125  tools=(     "bwa"     "blast"     "samtools"     "bedtools"     "spades"     "bcftools"     "fastp"     "multiqc" )
  126  # Install each tool
  127  for i in "${!tools[@]}"; do     tool="${tools[$i]}";     step=$((i + 6));     print_status "Step $step: Installing $tool through the bioconda channel...";          if conda install -c bioconda "$tool" -y; then         print_status "$tool installed successfully ✓";     else         print_error "Failed to install $tool";         exit 1;     fi;     echo; done
  128  history
(base) serahseriki001@cloudshell:~$ #End of project 2
