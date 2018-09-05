[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1342306.svg)](https://doi.org/10.5281/zenodo.1342306)

# Condo: Simulated codon-optimized CDS dataset

## Download

The most recent version of the Condo dataset is available for download in the HDF format at [Zenodo](https://doi.org/10.5281/zenodo.1342306).

To load the dataset using Pandas:
```python
    import pandas as pd
    df = pd.read_hdf("condo-0.1.3.h5", "condo")
```

## Contributing

To work on creating new versions of the dataset, you will first need to clone the repository using:

    $ git clone https://github.com/Benjamin-Lee/condo.git

Then, `cd` into the repo and run the following command to download the required packages:

    $ pip install -r requirements.txt

Note that the notebook is written in Python 3.6, so you will require at least that version.

## Version Information

### v0.1.3

The Condo v0.1.3 dataset contains 395,071 prokaryotic reference CDSs from RefSeq, of
which half have been codon optimized. All the input sequences are unique,
unambiguous, and have lengths divisible by three. Codon-optimized sequences are
targeted towards either highly expressed genes (`heg`) or towards overall genome
CUB (`genome`), [as calculated from
RefSeq](hive.biochemistry.gwu.edu/review/codon). The method by which the
sequences were codon optimized was either the one-amino-acid-one-codon
(`cai_max`) approach, in which the most used codon for each amino acid is used, or the
multinomial method, in which codons for amino acids are chosen with likelihoods
corresponding to their abundance in the target set (`multinomial`).

Data Summary:

    +-------------------------------+-----------+-------------+-------------+-------------+-------------------------------+
    |            sequence           | optimized |    method   | trans_table | target_type |          target_name          |
    +-------------------------------+-----------+-------------+-------------+-------------+-------------------------------+
    | TCTAATAGAACTCCTAGAAGATTTAG... |     1     |   cai_max   |      11     |    genome   | Leptospira interrogans ser... |
    | AAAAAAAAATTAGTTATGACAGCATT... |     1     |   cai_max   |      11     |     heg     |        linno.heg.fasta        |
    | GAATTCGCTATCGCTGCTGTTTTCAT... |     1     |   cai_max   |      11     |     heg     |       vfisc12.heg.fasta       |
    | GAAAAAGCTCAACAAGTATGGGTTGC... |     1     | multinomial |      11     |     heg     |         hduc.heg.fasta        |
    | CCGGCGTGCGAACTGCGCCCGGCGAC... |     1     |   cai_max   |      11     |    genome   |        Escherichia coli       |
    | AAGTTGTCGACCTGCTGCGCCGCCCT... |     1     | multinomial |      11     |    genome   | Mycobacterium tuberculosis... |
    | ATCACCCTGAACCACTACCTGGCCGT... |     1     | multinomial |      11     |     heg     |         chvi.heg.fasta        |
    | AAGATCACCGACATCAAGTTCGAAAA... |     1     |   cai_max   |      11     |     heg     |         paer.heg.fasta        |
    | CCGACCTCGCGGAGCAGCCGCCAGCC... |     1     | multinomial |      11     |    genome   |     Pseudomonas aeruginosa    |
    | ACATCATCAACAAAAATTAATGCATC... |     1     |   cai_max   |      11     |    genome   |  Staphylococcus aureus T47161 |
    +-------------------------------+-----------+-------------+-------------+-------------+-------------------------------+
    [395071 rows x 6 columns]

### Before v0.1.3

Versions before v0.1.3 were unstable and used for internal testing.
