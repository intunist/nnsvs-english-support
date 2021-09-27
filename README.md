# nnsvs-english-support
Hed and supporting files for English NNSVS Dataset Creation

This repo contains the files required to create an englsih dataset for use in NNSVS.
Additionally, instructions and examples are provided (or will be provided) for the labeling process.

The phoneme set is based on arpabet has been carefully selected to be compatible with as many English-speaking dialects as possible.
___
## Additional Info and Directions

The HED file was written by hand for NNSVS, it may not work in other tools as-is.
Two hed files are included. A minimal and full hed file. Both should work for NNSVS but using the full hed is suggested.

"DynamiVox English NN Phoneme Set v[x.x.x].txt" is a list of DynamiVox phonemes along with explanations of these phonemes.
Example words are provided for both US and UK English. If no UK example is provided then the example is the same for both.
This phoneme set is NOT COMPLETELY COMPATIBLE with Arpabet.
There are several additions/changes that cause the DynamiVox phoneme set to not be 1:1.
However, the basic phoneme section should be about the same.

"DynamiVox Phone Ref.txt" is a cleaned up phoneme document for reference while labeling.

the /dic folder contains several files
/english.conf - phoneme information
/english.macron
/english.table - syllabified English dictionary
/english1.table - non-syllabified English dictionary
/table credit.txt - credits for dictionaries

the /LAB_EXAMPLES folder contains EXAMPLES ON HOW TO LABEL singing.
These micro-datasets cannot be trained and are for reference only.
Usage of these datasets beyond this is strictly prohibited.
Multiple dialects are included to assist in properly labeling speech.
Please refer to "LABEL_HOWTO.txt" in the /LAB folder for more information.

NOTE: please change the value of "in_dim" in \train\conf\train\*\model\*.yaml
The values should be set as follows if using "DynamiVox English NNSVS.hed":

acoustic_conv.yaml: 496
acoustic_mdn.yaml: 496
duration_lstm.yaml: 492
duration_mdn.yaml: 492
timelag_ffn.yaml: 492
timelag_mdn.yaml: 492

If you are using "DynamiVox English NNSVS MINIMAL.hed", use the following values:

acoustic_conv.yaml: 349
acoustic_mdn.yaml: 349
duration_lstm.yaml: 345
duration_mdn.yaml: 345
timelag_ffn.yaml: 345
timelag_mdn.yaml: 345

Training will not work if these values are incorrect.

A the time of writing, NNSVS doesn't support multi-syllable words in the table. The UST/score will need to be written phonetically.
