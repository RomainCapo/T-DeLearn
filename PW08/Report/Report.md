# Report - DeepL PW08
* Romain Capocasale
* Jean Demeusy
* 29.04.2021

## Exercice 3
### Simple CNN
| CNN | Architecture                                                                                                                       | Acc. train % | Acc. test% |
|-----|------------------------------------------------------------------------------------------------------------------------------------|--------------|------------|
| 1   | Layer1 : CONV D=32, w=h=3, S=1, P='same', activation='relu;  Layer2 : MAXPOOL S=1, size=2; Layer3 : DENSE 10, activation='softmax' |     57.0     |    51.5    |

Loss/acc plot:

![Baseline_score.PNG](Baseline_score.PNG)

Discussion from previous exercice : 

### Deeper CNN
| CNN | Architecture                                                                                                                       | Acc. train % | Acc. test% |
|-----|------------------------------------------------------------------------------------------------------------------------------------|--------------|------------|
| 1   | Layer1 : CONV D=32, w=h=3, S=1, P='same', activation='relu;  Layer2 : CONV D=32, w=h=3, S=1, P='same', activation='relu; Layer3 : MAXPOOL S=1, size=2; Layer4 : DROPOUT : 0.25; Layer4 : CONV D=64, w=h=3, S=1, P='same', activation='relu; Layer5 : DENSE 10, activation='softmax'|     92.0     |    71.1    |
| 2   | Layer1 : CONV D=32, w=h=3, S=1, P='same', activation='relu;  Layer2 : CONV D=32, w=h=3, S=1, P='same', activation='relu; Layer3 : MAXPOOL S=1, size=2; Layer4 : DROPOUT : 0.5; Layer5 : CONV D=32, w=h=3, S=1, P='same', activation='relu; Laye6 : DROPOUT : 0.5; Layer7 : DENSE 10, activation='softmax'|     68.9    |    71.5    |
| 3   | Layer1 : CONV D=32, w=h=3, S=1, P='same', activation='relu;  Layer2 : CONV D=32, w=h=3, S=1, P='same', activation='relu; Layer3 : MAXPOOL S=1, size=2; Layer4 : DROPOUT : 0.5; Layer5 : CONV D=32, w=h=3, S=1, P='same', activation='relu; Laye6 : DROPOUT : 0.5; Layer7 : DENSE 128, activation='relu'; Layer8 : DROPOUT ; Layer9 : DENSE 10, activation='softmax'|     65.80    |    69.4    |
| 4   | LLayer1 : CONV D=32, w=h=3, S=1, P='same', activation='relu; Layer2 : DROPOUT 0.2;Layer3 : CONV D=32, w=h=3, S=1, P='same', activation='relu; Layer4 : MAXPOOL S=1, size=2;Layer5 : CONV D=64, w=h=3, S=1, P='same', activation='relu; Layer6 : DROPOUT 0.2;Layer7 : CONV D=64, w=h=3, S=1, P='same', activation='relu; Layer8 : MAXPOOL S=1, size=2;Layer9 : CONV D=128, w=h=3, S=1, P='same', activation='relu; Layer10 : DROPOUT 0.2;Layer11 : CONV D=128, w=h=3, S=1, P='same', activation='relu; Layer12 : MAXPOOL S=1, size=2;Layer13 : DROPOUT 0.2;Layer14 : Dense 1024, activation='relu'Layer15 : DROPOUT 0.2;Layer16 : Dense 512, activation='relu'Layer17 : DROPOUT 0.2;Layer18 : Dense 10, activation='softmax'|     80.8    |    76.3    |

CNN 1 Loss/acc plot:

![1_score.PNG](1_score.PNG)

CNN 2 Loss/acc plot:

![2_score.PNG](2_score.PNG)

CNN 3 Loss/acc plot:

![3_score.PNG](3_score.PNG)

CNN 4 Loss/acc plot:

![4_score.PNG](4_score.PNG)

Discussion : 
It can be seen that the best result is obtained with the 4th CNN architecture. This architecture has more Convolution/Maxpooling layer and with more filter on the convolution layer. This configuration also has 2 Dense layers (one of 1024 and one of 512) compared to the others. We also notice that this configuration does not overfit the data (compared to the first configuration for example). This is the 4th configuration with an accuracy of 76.3 on the test set which is retained.
