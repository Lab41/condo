# condo
Simulated codon optimized CDS dataset

## Contributing
To work on creating new versions of the dataset, you will first need to clone the repository using:

    $ git clone

Then, `cd` into the repo and run the following command to download the required packages:

    $ pip install -r requirements.txt

Note that the notebook is written in Python 3.6, so you will require at least that version.

## Version Information

### v0.1.1

The Condo v0.1.1 dataset contains 395,189 prokaryotic reference CDSs from RefSeq, of
which half have been codon optimized. All the input sequences are unique. Codon
optimized sequences are targeted towards either highly expressed genes (`heg`) or
towards overall genome CUB (`genome`), [as calculated from
RefSeq](hive.biochemistry.gwu.edu/review/codon). The method by which the
sequences were codon optimized was either the one-amino-acid-one-codon (`cai_max`) in which the most used codon for each amino acid is used or the
multinomial method in which codons for amino acids are chosen with likelihoods
corresponding to their abundance in the target set (`multinomial`).

Data Summary:

    +-------------------------------+-----------+-------------+-------------+-------------+
    |            sequence           | optimized |    method   | trans_table | target_type |
    +-------------------------------+-----------+-------------+-------------+-------------+
    | AAAACTGAAATTTGGAATGGACATAT... |     1     |   cai_max   |      11     |    genome   |
    | ACAGCAGAAACATTAATTGCATCTTT... |     1     |   cai_max   |      11     |     heg     |
    | AACCACCAACTAATCTTCCGTGATGA... |     1     |   cai_max   |      11     |     heg     |
    | CCAATTACTGGTGTTTTAGCGGATCA... |     1     | multinomial |      11     |     heg     |
    | ACAGGTCTAGGCATCGCAAGCACAGC... |     1     | multinomial |      11     |     heg     |
    | ACCACCTTCGCCGAACTGGGCCTGTC... |     1     |   cai_max   |      11     |     heg     |
    | GCTCCTGCAGAAACGTCACGTGTACA... |     1     | multinomial |      11     |    genome   |
    | GGCTTCACCGACGAAACCGTGCGCTT... |     1     |   cai_max   |      11     |     heg     |
    | AAAGATTGGGAATACAACGAACTGCT... |     1     |   cai_max   |      11     |     heg     |
    | TCAAAACCAGCACCAAAATTTTTAAC... |     1     |   cai_max   |      11     |    genome   |
    +-------------------------------+-----------+-------------+-------------+-------------+
    +-------------------------------+
    |          target_name          |
    +-------------------------------+
    | Leptospira interrogans ser... |
    |        linno.heg.fasta        |
    |       vfisc12.heg.fasta       |
    |         hduc.heg.fasta        |
    |         sloi.heg.fasta        |
    |       baboc12.heg.fasta       |
    |     Staphylococcus aureus     |
    |         rmet.heg.fasta        |
    |         ecar.heg.fasta        |
    |  Staphylococcus aureus W25814 |
    +-------------------------------+
    [395189 rows x 6 columns]
