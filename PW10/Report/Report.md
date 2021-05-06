# T-DeLearn PW10
* Romain Capocasale
* Jean Demeusy

## Exercice 1
### A
Summary of sequential architecture : 
![SequentialParam.PNG](SequentialParam.PNG)

Score of sequential : 
![SequentialScore.PNG](SequentialScore.PNG)

Summary of functional architecture : 
![FunctionalParam.PNG](FunctionalParam.PNG)

Score of functional : 
![FunctionalScore.PNG](FunctionalScore.PNG)

We can can that, the two model have the same number of parameters and the scores is slightly almost similar.

### B
| Model | Architecture description | Acc. train | Acc. test |
|-----|--------------------------|------------|-----------|
|  1 - multiple path| BRANCH1:CONV(D=32, w=h=3, S=1, P=same, act=relu)-DROPOUT(0.2)-MAXPOOL(S=1, size=2)-FLATTEN; BRANCH2:CONV(D=32, w=h=6, S=1, P=same, act=relu)-DROPOUT(0.2)-MAXPOOL(S=1, size=2)-FLATTEN; CONCAT(BRANCH1, BRANCH2); DENSE(100, act=relu); DENSE(10, softmax)  | 0.9020 | 0.6517 |
|  2 - multiple features| BRANCH1:CONV(D=32, w=h=3, S=1, P=same, act=relu)-DROPOUT(0.2)-MAXPOOL(S=1, size=2)-FLATTEN; BRANCH2(BRANCH1):CONV(D=32, w=h=3, S=1, P=same, act=relu)-DROPOUT(0.2)-MAXPOOL(S=1, size=2)-FLATTEN; BRANCH3(BRANCH2):CONV(D=32, w=h=3, S=1, P=same, act=relu)-DROPOUT(0.2)-MAXPOOL(S=1, size=2)-FLATTEN; CONCAT(BRANCH1, BRANCH2, BRANCH3); DENSE(100, act=relu); DENSE(10, softmax)  | 0.8658 | 0.6945 |
|  3 - multiple features| BRANCH1:CONV(D=32, w=h=3, S=1, P=same, act=relu)-DROPOUT(0.2)-MAXPOOL(S=1, size=2)-FLATTEN; BRANCH2(BRANCH1):CONV(D=32, w=h=3, S=1, P=same, act=relu)-DROPOUT(0.2)-MAXPOOL(S=1, size=2)-FLATTEN; BRANCH3(BRANCH2):CONV(D=32, w=h=3, S=1, P=same, act=relu)-DROPOUT(0.2)-MAXPOOL(S=1, size=2)-FLATTEN; CONCAT(BRANCH1, BRANCH2, BRANCH3); DENSE(64, act=relu); DROPOUT(0.2); DENSE(10, softmax)  | 0.8216 | 0.7153 |
  4 - multiple path| BRANCH1:CONV(D=32, w=h=3, S=1, P=same, act=relu)-DROPOUT(0.2)-MAXPOOL(S=1, size=2)-CONV(D=64, w=h=3, S=1, P=same, act=relu)-DROPOUT(0.2)-MAXPOOL(S=1, size=2)-FLATTEN; BRANCH2(BRANCH1):CONV(D=32, w=h=3, S=1, P=same, act=relu)-DROPOUT(0.2)-MAXPOOL(S=1, size=2)-CONV(D=64, w=h=6, S=1, P=same, act=relu)-DROPOUT(0.2)-MAXPOOL(S=1, size=2)-FLATTEN;  CONCAT(BRANCH1, BRANCH2); DENSE(50, act=relu); DROPOUT(0.2); DENSE(10, softmax)  | 0.6765 | 0.6891 |

Model 1 Loss/Accs : 
![Model1Plot.PNG](Model1Plot.PNG)

Model 2 Loss/Accs : 
![Model2Plot.PNG](Model2Plot.PNG)

Model 3 Loss/Accs : 
![Model3Plot.PNG](Model3Plot.PNG)

Model 4 Loss/Accs : 
![Model4Plot.PNG](Model4Plot.PNG)

### Discussion 
It can be seen that the model with the best accuracy is model number 3 with multiple features. We also see that the first 3 models overfit, this problem can be avoided by using data augmentation which has not been implemented. The 4th model overfits the least and seems the most stable.

We notice with this lab and the 2 previous ones that the accuracy of the models is around 0.70% and cannot be significantly exceeded despite all attempts.

Translated with www.DeepL.com/Translator (free version)