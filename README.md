# nnsvs-english-support
HED and supporting files for English NNSVS Dataset Creation
<br/>Now maintained by Intunist.

This repo contains the files required to create an English dataset for use in NNSVS.
Additionally, instructions and examples are provided (or will be provided) for the labeling process.

The phoneme set is based on arpabet has been carefully selected to be compatible with as many English-speaking dialects as possible.

NOTE: A pretrained model for English is not available at this time. Expect 8+ hours of audio to be required for a very high quality result.
The estimated amount of audio required for a somewhat decent model is about 4 hours (without silence). A prototype can be made with less (~1 hour).

Here is an example of a model trained with an 8.5 MINUTE dataset from HydroChromatic.

https://user-images.githubusercontent.com/16280813/153196769-54e76249-ebd6-4df5-8e9b-846e48e22035.mp4

## Additional Info and Directions

The HED file was written by hand for NNSVS, it may not work in other tools as-is.
Two hed files are included. A minimal and full hed file. Both should work for NNSVS but using the full hed is suggested.

"DynamiVox English NN Phoneme Set v[x.x.x].txt" is a list of DynamiVox phonemes along with explanations of these phonemes.
Example words are provided for both US and UK English. If no UK example is provided then the example is the same for both.
This phoneme set is NOT COMPLETELY COMPATIBLE with Arpabet.
There are several additions/changes that cause the DynamiVox phoneme set to not be 1:1.
However, the basic phoneme section should be about the same.

"DynamiVox Phone Ref.txt" is a cleaned up phoneme document for reference while labeling.

the /dic folder contains several files:  
/english.conf - phoneme information  
/amepd_dvx.table - DYVAUX (heavily) modified [AMEPD](https://github.com/rhdunn/amepd) dictionary  
/blank.table - basic dictionary for phonetic training  
/table credit.txt - credits for dictionaries  

the /LAB_EXAMPLES folder contains EXAMPLES ON HOW TO LABEL singing.
These micro-datasets cannot be trained and are for reference only.
Usage of these datasets beyond this is strictly prohibited.
Multiple dialects are included to assist in properly labeling speech.
Please refer to "LABEL_HOWTO.txt" in the /LAB folder for more information.

You can change the hed file in config.yaml, this is found at `/train/config.yaml`.

NOTE: please change the value of "in_dim" in `/train/conf/train/*/model/*.yaml`
The values should be set based on the values provided in the HED files.
Training will not work if these values are incorrect.

A the time of writing, NNSVS doesn't appear to support multi-syllable words in the table. The UST/score will need to be written phonetically.
For phonetic usts, don't use english.table, use blank.table.
Otherwise it may try to match phonemes to pronuncations and fail with `ValueError: could not broadcast input array from shape (###,476) into shape (###,476)`.

Version 0.6.0 adds support for ENUNU's flag system for swapping voice timbre.

Here is a list of the currently supported flags:

| Flag | Purpose               |
|------|-----------------------|
| F    | falsetto              |
| H    | head voice            |
| SF   | soft                  |
| ST   | strong                |
| OPN  | open_wide_vowel       |
| CLS  | closed_narrow_vowel   |
| W    | whisper_devoiced      |
| S    | false_cord_fry_scream |
| G    | guttural_scream_growl |
| B    | bright_resonance      |
| D    | dark_resonance        |
| Y    | young_higher_formant  |
| O    | older_lower_formant   |
| T    | thin                  |
| R    | fry_rattle            |
| N    | nasal                 |
| HPY  | happy                 |
| SAD  | sad                   |
| MAD  | mad                   |
| 1    | additional_1          |
| 2    | additional_2          |
| 3    | additional_3          |
