# Cognitive Psychology Workshop 1
## Workshop 1 by Belchenko Alisa
### Experiment description:
* The online experiment consisted of three blocks, in each of which participants were shown photographs of people with different emotions (anger, joy, neutrality) of different races: black, white and Asian.
* In one block, photographs with only one emotion were shown, but there were photographs of each of the stated races.
* Each block took place in two stages: memorization and the experiment itself. At each stage, the photographs described earlier were quickly switched, but at the memorization stage, the subjects also had to answer whether they had seen these photographs before (for this, the right ("right") and left ("left") arrow keys on the keyboard were used to indicate "yes, I saw" and "no, I didn't see", respectively).
* Accuracy of answers and reaction time were evaluated.
* Description of IV (independent variable) and DV (dependent variable):
  * IV1 - emotion on the person's face in the presented photograph (values: anger, joy, neutrality)
  * IV2 - race (values: black, white, Asian)
  * DV1 - accuracy of the answer to the question "Have you seen this photograph before?" (values: 0 - incorrect, 1 - correct)
  * DV2 - response time to the question "Have you seen this photograph before?" (real number)

### Calculations performed with the data:
* Data preprocessing: during this, the data obtained after the experiment was carried out were extracted, which we will need for further analysis. The following parameters were extracted (all from the experiment stage):
   1. **img** - the name of the image that was presented at the experiment stage (in which the race and emotion of the person depicted in the photograph are encoded)
   2. **cond** - which block of the experiment it was, i.e., which emotion was presented in this block (values: neutral, positive, negative)
   3. **key_resp.keys** - which button was pressed when answering the question "Have you seen this photograph before?" (values: right for the answer "yes, I saw", left for the answer "no, I didn't see")
   4. **key_resp.rt** - reaction time (time until one of the keys was pressed)
   5. **corr** - correctness of the answer (0 or 1)
* Metric calculation: the following values were calculated:
   1. **Number of hits** - "1" if the photograph was actually shown before and we pressed the "right" button, and "0" otherwise.
   2. **Number of false alarms (FA)** - "1" if the photograph was not shown before and we pressed the "right" button, and "0" otherwise.
   3. **Probabilities of hits and false alarms (p)** - the average of the Hits and FA values for different conditions (first for emotions, then for races).
   4. **Z-value (z)**- the inverse standard normal distribution for the calculated probabilities.
   5. **Sensitivity** - a measure that reflects the ratio of signals (photographs that were actually shown before) to noise (photographs that were not shown) in signal processing theory. This is the difference between the z-scores for correct answers and false alarms.
   6. **Criterion** - the measure of the used criterion: k*zhits+zfa, where k = -0.5.

### Graphical representation of the results obtained
* The second graph (in file main.ipynb) shows the percentage of confirmations for different emotions (i.e., the percentage of hits).
* The first graph (in file main.ipynb) shows the percentage of rejections for different emotions (i.e., the percentage of false alarms)
Additional tasks also included similar graphs for races:

### Interpretation of the results obtained:
#### For emotions:
I obtained the following sensitivity:
* For neutral emotions   1.88
* For positive emotions   1.73
* For negative emotions   0.9

The emotions described above were presented in this order. It can be noticed that the sensitivity decreases with each block, and in the last block (negative emotions) it is very low. This can be explained by the fact that I did not fully understand the conditions, and I marked that I had seen people, even if they were presented only in the previous blocks with a different emotion, since the question was "Have you seen this person before?", and not "Have you seen this photograph before", so my results cannot be interpreted in terms of emotional bias at all.

I obtained the following criteria:
* For neutral emotions   -0.94
* For positive emotions   -0.87
* For negative emotions   -045

All my criteria were liberal, which means that I was more inclined to give positive answers ("yes" to the question of whether I had seen the photograph before), but this can be explained by what I described above, i.e., that I misunderstood the conditions and generally gave "yes" answers more often.

#### For races:
Similar work was also done for different races, i.e., the letters that correspond to the races ("a", "b", "w") were extracted from the picture names, and all the metrics described above were also calculated for them.

Due to my erroneous perception of the conditions, the results cannot be reliably interpreted, but in the case of races, the obtained numbers have much more meaning than for emotions, since the races were presented in a mixed order, and not in blocks, but they are still biased due to the fact that I could mark "yes" if the person was also in the previous blocks, and not only in this one.

I obtained the following sensitivity:
* For Asians ("a")   0.71
* For blacks ("b")   1.93
* For whites ("w")   1.55

It is noticeable that the sensitivity is significantly higher for blacks and whites than for asians, which does not correspond to the theory of "Own-race bias". My hypothesis regarding this difference is that I believe I have watched many videos and TV series since childhood, in which representatives of the white and black races were presented, but I have watched very few videos with representatives of the Asians.

I obtained the following criterion:
* For Asians ("a")   0.35
* For blacks ("b")   0.97
* For whites ("w")   -0.78

For all races criterion is liberal, which can also be explained by my misunderstanding of the condition and the fact that according to my condition, I should have answered "yes" more often than in the intended condition.
