This is a list of the currently supported phonemes, examples, and other various notes.

This phoneme set **covers all English phonetic sounds across ALL dialects**, utilizing NNSVS's phoneme context. No new phonemes will be added as they will not improve the phoneme set or model capability regardless of dialect.
### Vowels - monophthongs:
| phoneme | US Example        | UK Example   | Description                                                                                            |
|---------|-------------------|--------------|--------------------------------------------------------------------------------------------------------|
| ah      | hUt               | #            | 'uh' sound.                                                                                            |
| aa      | clOck             | fAther, plOt | open ah.                                                                                               |
| ao      | bOUght, stORy     | nAUght, cORe | un/rounded aw. **US English uses unrounded by itself but rounded for rhotic. It's fine.                |
| ae      | bAt               | bAth, bAt    | "at" sound for US. Contextual "ah/ae" for UK and similar.                                              |
| ax      | commA, parrOt     | #            | schwa.                                                                                                 |
| iy      | bEAt,petIt        | #            |                                                                                                        |
| ih      | sIt               | #            |                                                                                                        |
| uh      | bOOk, nOOk        | #            |                                                                                                        |
| uw      | bOOt, sUIt        | #            |                                                                                                        |
| eh      | bEt, plEthera     | #            |                                                                                                        |
| er      | bIRd, nERd        | bIRd         |                                                                                                        |
### Vowels - diphthongs:
| phoneme | US Example        | UK Example | Description                                                                                            |
|---------|-------------------|------------|--------------------------------------------------------------------------------------------------------|
| ay      | bIte              | #          |                                                                                                        |
| a       | (optional)        | #          | Stylistic dropping of diphthong ending. Completely unnecessary and handled contextually.               |
| ey      | bAIt              | #          |                                                                                                        |
| e       | (optional)        | #          | Stylistic dropping of diphthong ending. Completely unnecessary and handled contextually.               |
| oy      | bOY               | #          |                                                                                                        |
| aw      | plOW, abOUt       | #          |                                                                                                        |
| ow      | bOAT              | #          |                                                                                                        |
| o       | (optional)        | #          | Stylistic dropping of diphthong ending. Completely unnecessary and handled contextually.               |
### Consonants:
Voice and unvoiced equivalents are paired (ex: k/g, t/d)
| phoneme | US Example        | UK Example | Description                                                                                            |
|---------|-------------------|------------|--------------------------------------------------------------------------------------------------------|
| p       | PoP               | #          |                                                                                                        |
| b       | BoB               | #          |                                                                                                        |
| t       | TaT               | #          |                                                                                                        |
| d       | DaD               | #          |                                                                                                        |
| k       | CaKE              | #          |                                                                                                        |
| g       | GaG               | #          |                                                                                                        |
| s       | SaS               | #          |                                                                                                        |
| z       | ZooS              | #          |                                                                                                        |
| ch      | CHurCH            | #          |                                                                                                        |
| jh      | JuDGE             | #          | Makes 'dg' sound for end of words. like [d][zh] or /dZ/ in xsampa.                                     |
| sh      | Ship, puSH        | #          |                                                                                                        |
| zh      | pleaSure          | #          | The 'judge' example is [j ah d zh], not [j ah zh]. To avoid any confusion.                             |
| f       | FlooF             | #          |                                                                                                        |
| v       | Verge, nerVe      | #          |                                                                                                        |
| hh      | Happy             | Herb       | syllable onset only. Use [exh] for end-of-note exhales.                                                |
| th      | THin, myTH        | #          |                                                                                                        |
| dh      | THis, widTH       | #          |                                                                                                        |
| n       | NaNNy, paN        | #          |                                                                                                        |
| m       | MoM, MoMent       | #          |                                                                                                        |
| ng      | baNG, suNG        | #          |                                                                                                        |
| w       | Wisp              | #          | syllable onset only.                                                                                   |
| y       | Yes               | #          | syllable onset only.                                                                                   |
| r       | Road, caR         | caR        | rhotic shares same phoneme. It's fine. UK dropped r as well.                                           |
| l       | List, caLL        | #          | dark L shares same phoneme. It's fine.                                                                 |
| q       | we-eat batten     | bottom     | glottal stop and vowel separator. NOT vocal fry.                                                       |
| dx      | buTTer            | shuTup     | tapped/flapped d/tt. Use in UK English is spotty.                                                      |
### Syllabic vowel-like-consonants:
Consonants that have a vowel-like quality in terms of sustain. **Technically optional.**
| phoneme | US Example        | UK Example | Description                                                                                            |
|---------|-------------------|------------|--------------------------------------------------------------------------------------------------------|
| el      | peopLE, doubLE    |            | vowellike l, where l makes most of the syllable, otherwise [ax l]                                      |
| em      | bottOM            |            | vowellike m, where m makes most of the syllable, otherwise [ax m]                                      |
| en      | buttON            |            | vowellike n, where n makes most of the syllable, otherwise [ax n]                                      |
| eng     | sINGING, learnING |            | **REMOVED IN v0.3.1 DUE TO BEING COMPLETELY USELESS. USE [ih][ng] INSTEAD**                            |
### Non-English Phonemes
| phoneme | Description                                                                                            |
|---------| -------------------------------------------------------------------------------------------------------|
| rr      | Trilled r (like in spanish)                                                                            |
| rx      | Fricative r (like in german or french)                                                                 |
| x       | Voiceless velar fricative. Scottish/Welsh specific.                                                    |
### Utility phonemes:
Phonemes that aren't strictly vocal sounds but are useful in one way of another
| phoneme | Example          | Description                                                                                            |
|---------|------------------| -------------------------------------------------------------------------------------------------------|
| pau     | silence          | During unsung/silent periods.                                                                          |
| br      | [breath]         | **REMOVED IN v0.7.0 DUE TO MODEL INSTABILITY**                                                         |
| exh     | [exhale]         | end breaths, end of phrase exhale. devoiced. Label consonant coda.                                     |
| axh     | [release]        | voiced variation of [exh]. voiced schwa exhale/release. Label as consonant coda.                       |
| ct      | [closure-toggle] | override the default state of a consonant's closure. Entirely optional.                                |
| cl      | [held stop]      | Held stop/plosive consonant. For when the silence is held. Similar to Japanese usage but not syllabic. |
| vf      | [vocal fry]      | vocal fry. Can be used as a consonant OR on it's own note.    
