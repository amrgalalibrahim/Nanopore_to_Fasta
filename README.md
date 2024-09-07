# Nanopore_to_Fasta
Nanopore barcode sequencing to final single fasta

This script automates the processing of Nanopore sequencing data, from raw fastq.gz files to a final assembled FASTA sequence for each barcode/sample.

Author: Amr Galal (amrgalalibrahim@gmail.com)
Supervisor: Prof. Edson Adriano (adriano@unifesp.br)

Requirements:

Software:
NanoFilt
Porechop
Flye
seqret (depends on EMBOSS)
Environment:
Bash shell
Recommended: Conda for easier Flye installation
Installation

Install required tools using sudo apt install or conda install as indicated in the script comments.
Usage

Configure Input/Output:

Replace your_input_directory and your_output_directory with the actual paths to your data.
Your input directory should contain subdirectories, each representing a barcode/sample, with fastq.gz files inside.
Run the Script:

Make the script executable: chmod +x script_name.sh
Execute: ./script_name.sh
Important:

<estimated_genome_size>: You MUST provide the estimated genome size for Flye to work properly. Replace <estimated_genome_size> in the script with the appropriate value.
What the Script Does

For each barcode directory:

Concatenates all fastq.gz files.
Filters and trims reads using NanoFilt and Porechop.
Optionally, performs error correction (uncomment and configure if needed).
Assembles the reads using Flye.
Extracts the final consensus sequence into a ${barcode_name}_final.fasta file.
Output

The final FASTA sequences are located in the output directory, within subdirectories named after each barcode.
Key Points

The script assumes a specific directory structure for input data.
Error correction is optional and may not be necessary for all datasets.
Flye's --genome-size parameter is crucial for successful assembly.
If using the direct Flye download, ensure the path in the script is correct.
Troubleshooting

If you encounter errors, check:
Correct installation of all tools.
The provided --genome-size for Flye.
The directory structure of your input data.
If using the direct Flye download, ensure the path in the script is correct.
Additional Notes

This script provides a basic workflow. You may need to adapt it for specific needs or incorporate additional quality control steps.
Consider exploring alternative assemblers or polishing tools for further optimization.
