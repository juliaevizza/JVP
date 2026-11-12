# JVP_018 annotation cleanup

The original 5,835 bp circular DNA sequence and coordinate system are unchanged.
Input: `JVP_018.gbk`. Output: `JVP_018_e30-chip_annotated.gbk`.

## e30-chip sequence comparison

- Supplied protein: 201 aa.
- Corresponding observed segment: 197 aa, reverse strand, 3196–3786.
- One exact alignment omits reference residues 22–25, **SGAS**; all other reference residues match.
- Reference local sequence: `DYEGGSGSGSGASRLN`; observed: `DYEGGSGSGRLN`.
- Full CDS: `complement(3163..3789)`, 627 bp including stop, 208 translated aa.
- Full encoded product: `M` + observed segment + `VDGAHHHHHH` + stop.
- 6xHis tag: `complement(3166..3183)`.
- Comparison uses the supplied consensus and protein reference, not raw sequencing reads.
  It does not establish whether the discrepancy arose during cloning, sequencing, or reference preparation.

## Annotation changes

Added the sequence-derived e30-chip CDS with translation, shortened linker, C-terminal spacer, and 6xHis tag.
Retained backbone feature coordinates and match provenance; consolidated automatic metadata into readable notes.
Sorted features by genomic position and changed record name from JV_5 to JVP_018.

- Replaced overlapping automatic match: STUB1 (fragment) (complement(3196..3723)).
- Converted partial CDS to misc_feature: TcR (partial match) (5394..5685).
- Converted partial CDS to misc_feature: TcR (partial match) (3898..4177).
- Converted origin-spanning YPB1_ECOLX hit to a homology misc_feature.
- Converted partial CDS to misc_feature: SET1 (partial match) (complement(3101..3150)).
- Replaced overlapping automatic match: CDH3 (fragment) (complement(3727..3792)).

## Validation

Original ORIGIN block preserved byte-for-byte in text; sequence is 5,835 unambiguous A/C/G/T bases.
CDS translation, tag translation, reference alignment, feature coordinate bounds, and serialized translation verified.
Original input file unchanged. Sequence SHA-256 (uppercase bases): `6b306047b17a26940e04e37d9329e5ec65822908ae2b6ba2365280bb58b07dd0`.

## Protein sequences

Supplied reference:
```
PTAPPYDSLLVFDYEGGSGSGSGASRLNFGDDIPSALRIAKKKRWNSIEERRIHQESELHSYLSRLIAAERERELEECQRNHEGDEDDSHVRAQQACIEAKHDKYMADMDELFSQVDEKRKKRDIPDYLCGKISFELMREPCITPSGITYDRKDIEEHLQRVGHFDPVTRSPLTQEQLIPNLAMKEVIDAFISENGWVEDY
```

Observed corresponding segment:
```
PTAPPYDSLLVFDYEGGSGSGRLNFGDDIPSALRIAKKKRWNSIEERRIHQESELHSYLSRLIAAERERELEECQRNHEGDEDDSHVRAQQACIEAKHDKYMADMDELFSQVDEKRKKRDIPDYLCGKISFELMREPCITPSGITYDRKDIEEHLQRVGHFDPVTRSPLTQEQLIPNLAMKEVIDAFISENGWVEDY
```

Full translated CDS (terminal stop omitted):
```
MPTAPPYDSLLVFDYEGGSGSGRLNFGDDIPSALRIAKKKRWNSIEERRIHQESELHSYLSRLIAAERERELEECQRNHEGDEDDSHVRAQQACIEAKHDKYMADMDELFSQVDEKRKKRDIPDYLCGKISFELMREPCITPSGITYDRKDIEEHLQRVGHFDPVTRSPLTQEQLIPNLAMKEVIDAFISENGWVEDYVDGAHHHHHH
```
