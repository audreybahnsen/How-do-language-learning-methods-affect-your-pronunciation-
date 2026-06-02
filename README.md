# How do language learning methods affect your pronunciation?
Above is the official research question to prevent bias in subjects. Really, the research question was "Which language learning method is most effective for learning correct pronunciation?"

This is a benchmark study across 3 popular langauge learning methods for pronunciation. They are ELSA Speak, BurlingtonEnglish's SpeechTrainer. Additionally one other method is tested: using a "Golden Speaker". A "Golden Speaker" is synthesised speech that relays native pronunciation in a target language, in a voice similar to yours. This idea dates back to 1990, such as in the <a href="https://www.isca-archive.org/icslp_1990/nagano90_icslp.pdf" >Naguno and Ozawa's "English Speech Training using Voice Conversion"</a> paper.

## Set-up
Participants must:
1) not speak Swahili
2) be female

If participants were to speak Swahili, that would introduce a bias. And as for gender: pitch is the most slaient voice attribute and is therefore used as grounds of similarity. Recordings that subjects use as a reference in the 4th treatment (which is the mockup verison of having "Golden Speaker') are from native female speakers. Gender was randomly chosen here and because of this setting subjects must be female to match the pitch of their "Golden Speaker" recordings more closely.

18 Participants were recruited, amounting to 339 utterances observed.

### Before Stage
Participants are asked to record themselves pronouncing the 12 words they will see throughout the study.

<p float="left">
  <img width="40%" alt="gittotalwordlist" src="https://github.com/user-attachments/assets/db2a6aa4-ac71-4a71-936d-ecef904100ec" />
  <br><sub><b>The 12 Swahili words</b></sub>
</p>

### After Stage
The subjects' "After Stage" pronounciations are recorded throughout the study. Because the study goes through each language learning method (treatment) one by one, subjects record their pronunciations right after they have finished training with one method. In each method, there are 2 rounds of training. After, subjects do their "final recordings".

### Results
The effectiveness of each language learning method is calculated via comparing the "Before Stage" and "After Stage" recordings of each subject. Key: ELSA Speak treatment= method A, SpeechTrainer treatment= method B, Fluent Forever treatment= method C. The GS method was planned but recordings weren't uploaded due to a JSON bug. as this study will run for the future and this error is fixed, look for updates here- future results will include this method's results!

Before and after audio is transcribed using Whisper (ASR). The text transcriptions are then converted into phonemes using a grapheme-to-phoneme converter (G2P).

<img width="40%" alt="jamboconversion" src="https://github.com/user-attachments/assets/ec041267-eaa7-4651-b6f8-bfbe4950da3e" />
<br><sub><b>"jambo" means "hello" in Swahili</b></sub>

Phoneme Error Rate (PER) is then calculated on the phoneme sequences produced. PER is calculated via Levenshtein distance.

Repeated Measures ANOVA is then the statistical test used to make comparisons of subjects' recordings from method to method.

Therefore across 3 methods:

<b>Result set 1</b> Metric: Text-reference PER

<i>RM-ANOVA (mean PER ~ condition)</i>
F(3, 42) = 5.323
p = 0.00336
Greenhouse–Geisser corrected p = 0.01648
(ng2 ≈ 0.197)

<i>Mean change vs before (after − before PER; negative = better)</i>
A: mean −0.073
B: mean +0.479 (worse)
C: mean −0.013 (roughly flat)

<i>On average A slightly improves, B worsens, C is near-neutral.</i>

<b>Result set 2</b> Metric: PER computed against native MP3 reference

<b>Paired before vs after pronunciations</b>
(Improvement = PER_before − PER_after; positive = better)

<i>Method A (mkono/tumbo/mhandisi):</i>
n = 13, mean improvement +0.080
t = 0.775, p = 0.453 (ns), d ≈ 0.314

<i>Method B (maji/mvinyo/ndio):</i>
n = 9, mean improvement −0.417 (worse)
t = −2.400, p = 0.043 (significant), d ≈ 0.666

<i>Method C (jambo/kuona/wiki):</i>
n = 8, mean improvement −0.358 (worse)
t = −1.269, p = 0.245 (ns), d ≈ 0.571


<i>“Across-methods” RM-ANOVA on improvement</i>
F ≈ 0.368, p = 0.713 (small df however!)

Against the native speaker reference audio, A trends positive but not significant; B shows significant worsening; C trends negative but not significant.


Therefore, as of the current verison of this study, method A is most promising. Further data is to be collected.

Some subjects also provided feedback and said that seeing accuracy percentages (ELSA Speak mockup) was fun. This suggests that having a gamified metric within a language learning platform is more engaging.
