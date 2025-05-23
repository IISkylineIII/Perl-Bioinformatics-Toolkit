# Perl Bioinformatics Toolkit

## Description
This repository offers a curated set of essential Perl commands, scripts, and workflows commonly used in Bioinformatics and Statistical data processing. The aim is to enable reproducible analyses and simplify data manipulation tasks in sequence analysis, genomics, variant processing, and statistical reporting by providing clear, practical examples leveraging Perl’s powerful text and file handling capabilities.

## Pipeline Overview
The collection is organized into major categories demonstrating core Perl functionality relevant to bioinformatics workflows:

1. **Data Parsing and Preprocessing**
   - Reading and parsing data formats like FASTA, FASTQ, GFF, VCF
   - String manipulation and pattern matching with regular expressions
   - Data cleaning, filtering, and transformation using Perl data structures
   - Handling missing or inconsistent data entries

2. **Sequence and Genomic Data Analysis**
   - Sequence retrieval, reverse complement, translation, and motif search
   - Manipulating nucleotide and protein sequences
   - Parsing and summarizing variant call data (VCF processing)
   - Basic alignment parsing and format conversion

3. **Statistical Processing**
   - Simple descriptive statistics and summary computations
   - Integration with external statistical tools or inline calculations
   - Generation of statistical reports and formatted output

4. **Workflow Automation and Pipeline Integration**
   - Writing modular, reusable Perl scripts
   - Automating bioinformatics pipelines with system calls and file handling
   - Handling large datasets efficiently with memory management

5. **Visualization Preparation**
   - Preparing data files for downstream plotting tools (e.g., R, gnuplot)
   - Generating summary tables and intermediate files for visualization

## Example Commands and Usage

### Reading a FASTA file
```perl
use Bio::SeqIO;
my $seqio = Bio::SeqIO->new(-file => 'seqs.fasta', -format => 'fasta');
while (my $seq = $seqio->next_seq) {
    print $seq->id, "\n", $seq->seq, "\n";
}
```
## Reverse complement sequence

```
my $seq = "ATGCTAGC";
my $revcomp = reverse $seq;
$revcomp =~ tr/ACGTacgt/TGCAtgca/;
print $revcomp, "\n";
```

## Filtering lines from a tab-delimited file
```
open(my $fh, '<', 'data.tsv') or die $!;
while (<$fh>) {
    print if /^chr[1-9]/;  # only print lines starting with chr1-chr9
}
close $fh;
```


## Requirements
* Perl 5.10 or higher
* BioPerl modules (Bio::SeqIO, Bio::Tools::SeqStats, etc.)
* Standard Perl modules (Getopt::Long, File::Spec, etc.)

## References
* Bioinformatics Programming Using Perl, by Curtis Huttenhower, Sean D. Eddy, and others
* BioPerl Project: https://bioperl.org
* Learning Perl, by Randal L. Schwartz, brian d foy, and Tom Phoenix

## License
MIT License

