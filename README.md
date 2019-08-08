# RBH

* A wrapper Ruby script to generate reciprocal NCBI BLAST best hits or one way hits.

# Required

* NCBI BLAST+
* https://blast.ncbi.nlm.nih.gov/Blast.cgi

# Required Gem

* Bioruby (bio >= 1.5.1)
* Optparse_ex (optparse_ex >= 0.0.4)

# Usage

```
$ rbh [options]
    -1, --fasta1 file.fasta          Fasta file (required)
    -2, --fasta2 file.fasta          Fasta file (required)
        --[no-]tblastx               Use tblastx to nuc to nuc search (default: false, meaning without this option, use blastn)
    -o, --one_way                    One way blast best hit (fasta1:query, fast2:database) (default:off, reciprocal best hit)
    -t, --threads num                Num of threads (default:1)
        --exonave ave                Average Exon length (default:200, used for filtering blast hit alignment length)
    -f, --outfmt6                    outfmt 6 (default:non)
    -m, --maxtarget max              max_target_seqs (default:5)
    -r, --result directory           Output directory (default:.)
    -e, --evalue evalue              Evalue used for blast (default:1.0e-15)
    -b, --blast_bin_dir dir          Blast binary directory path (default:/usr/bin)

ex.
$ rbh -1 fast1.fa -2 fasta2.fa -t 8    #=> reciprocal best hits between fasta1.fa and fasta2.fa
$ rbh -1 fast1.fa -2 fasta2.fa -t 8 -o #=> one way blast hits, fasta1.fa as query and fasta2.fa as database
```
