# nnsvs-english-support
Hed and supporting files for English NNSVS Dataset Creation

This repo contains the files required to create an English dataset for use in NNSVS.
Additionally, instructions and examples are provided (or will be provided) for the labeling process.

The phoneme set is based on arpabet has been carefully selected to be compatible with as many English-speaking dialects as possible.

The estimated amount of audio required for a high quality dataset is 3-4 hours (without silence). A prototype can be made with less.

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
/english.macron  
/english.table - non-syllabified English dictionary  
/english1.table - syllabified English dictionary  
/blank.table - basic dictionary for phonetic training  
/table credit.txt - credits for dictionaries  

the /LAB_EXAMPLES folder contains EXAMPLES ON HOW TO LABEL singing.
These micro-datasets cannot be trained and are for reference only.
Usage of these datasets beyond this is strictly prohibited.
Multiple dialects are included to assist in properly labeling speech.
Please refer to "LABEL_HOWTO.txt" in the /LAB folder for more information.

You can change the hed file in config.yaml, this is found at `/train/config.yaml`.

NOTE: please change the value of "in_dim" in `/train/conf/train/*/model/*.yaml`
The values should be set as follows if using "DynamiVox_English_NNSVS.hed":

* acoustic_conv.yaml: 523
* acoustic_mdn.yaml: 523
* duration_lstm.yaml: 519
* duration_mdn.yaml: 519
* timelag_ffn.yaml: 519
* timelag_mdn.yaml: 519

If you are using "DynamiVox_English_NNSVS_MINIMAL.hed", use the following values:

* acoustic_conv.yaml: 370
* acoustic_mdn.yaml: 370
* duration_lstm.yaml: 366
* duration_mdn.yaml: 366
* timelag_ffn.yaml: 366
* timelag_mdn.yaml: 366

Training will not work if these values are incorrect.

A the time of writing, NNSVS doesn't appear to support multi-syllable words in the table. The UST/score will need to be written phonetically.
For phonetic usts, don't use english.table, use blank.table.
Otherwise it may try to match phonemes to pronuncations and fail with `ValueError: could not broadcast input array from shape (###,496) into shape (###,496)`.
___
Version v0.2.1 now includes an optional HED that adds support for adding suffixes to your dataset. The suffixes are OPTIONAL and for a small dataset you _should not_ use them.
For normal usage suffixes can be ignored.
Suffixes are primarily intended to isolate phonemes that may not meet the "goal" of your dataset.
Such as isolating belting notes in a dataset that is intended to be generally soft, or falsetto notes in a dataset that is meant to be powerful, etc.
| Suffix | purpose                                 |
| ------ | --------------------------------------- |
| \_ol   | Out of language (consonants + vowels)   |
| \_f    | (falsetto)                              |
| \_b    | (belt)                                  |
| \_d    | (devoiced/whisper)                      |
| \_c    | (creaky/vocal fry)                      |
| \_g    | (growl or false cord scream)            |
| \_gg   | (guttural scream/growl)                 |

Adding suffixes to a dataset with the intention of them being fully functional (as opposed to just being nused for isolation) requires you to add quite _a lot_ more audio. For a full 4 hour dataset, each additional suffix will require about 1.5-2 hours of additional audio each.
Suffixes may be useful for better targeting the tone of a dataset. (ex: If you are working on a strong dataset and some unwanted falsetto notes exist in tthe dataset, you could label them as [`ay_f`].)

NOTE: The usage of suffixes increases the RAM/VRAM requirements for training. You will want to use suffixes sparingly (don't use all of them at once in a dataset, limit it to ~2 types) and remove the ones you do not need from the HED file. English already requires a lot of vram and suffixes exacerbate this.
