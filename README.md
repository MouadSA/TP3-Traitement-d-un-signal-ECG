# TP3-Traitement-d-un-signal-ECG
TP3-Traitement-d-un-signal-ECG
 
 Objectifs:
Dans ce troisième Tp on cherche a Supprimer du bruit autour du signal produit par un électrocardiographefaire et faire la représentation temporelle et fréquentielle en utilisant la transformée de fourrier discrète sous le logiciel Matlab.

Introduction :
Un électrocardiogramme (ECG) est un test qui mesure l'activité électrique du cœur. Il est utilisé pour détecter des anomalies cardiaques telles que les troubles du rythme cardiaque, les infarctus du myocarde et les maladies cardiaques congénitales.

![image](https://user-images.githubusercontent.com/79712514/215355857-6bb4ba4c-9c54-42f6-a054-44f818eee3f7.png)
 L’onde P représente la première étape du cycle où les oreillettes (ou atriums) se contractent permettant le passage du sang, à travers les valves auriculoventriculaires, vers les ventricules. Ensuite, le complexe QRS symbolise à la fois la contraction ventriculaire (permettant l’éjection du sang vers les artères) notamment par le pic en R, dans le même temps,le relâchement des oreillettes entraîne le remplissage de celles-ci en attente d’un nouveau cycle).

L’onde T représente le relâchement des ventricules suite à leur contraction.L’enchaînement de ces complexes permet par ailleurs de déterminer la fréquence cardiaque, c’est-à-dire le nombre de cycle cardiaque par unité de temps. Une fréquence cardiaque normale est comprise entre 60 et 100 battements par minute, en dessous de cette valeur, le patient est en « bradycardie », au-dessus de cette valeur,le patient est en « tachycardie ».

Les signaux ECG sont contaminés avec différentes sources de bruits. Les bruits de hautes fréquences sont provoqués par l’activité musculaire extracardiaque et les interférences dues aux appareils électriques, et des bruits de basses fréquences provoqués par les mouvements du corps liés à la respiration, les changements physicochimiques induits par l’électrode posée sur la peau et les micro variations du flux sanguin. Le filtrage de ces bruits est une étape très importante pour faire un diagnostic réussi.

1 - Suppression du bruit provoqué par les mouvements du corps:

![image](https://user-images.githubusercontent.com/79712514/215355875-65f73574-d466-4e56-a2e7-5da2617a16f9.png)


Son spectre d'amplitude :

![image](https://user-images.githubusercontent.com/79712514/215355935-35b96a08-265c-4287-bae7-38e81efd6944.png)


Ensuite on procède a supprimer le bruit des mouvements du corps en utilisant un filtrage idéal passe haut et on trace la différence par rapport au signal d'origine

![image](https://user-images.githubusercontent.com/79712514/215355939-9f898ddc-1ae2-4c03-827c-7f2a024643eb.png)


2 - Suppression des interférences des lignes électriques 50Hz: ![image](https://user-images.githubusercontent.com/79712514/215355950-6268e13e-100d-4dc5-b33d-d1c4e4b0618e.png)


On remarque qu'il y a un bruit qu'on doit éliminer avec un filtrage notch 3 - Suppression des interférences des lignes électriques 50Hz : ![image](https://user-images.githubusercontent.com/79712514/215355972-ed52b6d9-b63e-4442-944c-4b2724a3ba30.png)


On remarque que ce signal est encore bruité quand on le compare avec le signal ECG qu'on doit avoir. Pour eliminer ce bruit on applique un filtrage pass bas pour eliminer les bruits de basses fréquences.

ECG 2 apres le filtrage notch avec ses spectres et le bruit qui doit etre eliminer

![image](https://user-images.githubusercontent.com/79712514/215356052-78227b78-9d3d-407e-8137-60eee898dc73.png)
 4 - Amélioration du rapport signal sur bruit : ![image](https://user-images.githubusercontent.com/79712514/215356059-2309ab4d-a571-4eaa-9c49-5dbe71b77537.png)


5 - Identification de la fréquence cardiaque avec la fonction d'autocorrélation : La fréquence cardiaque peut être identifiée à partir de la fonction d'autocorrélation du signal ECG. Cela se fait en cherchant le premier maximum local après le maximum global (à tau = 0) de cette fonction. On utilise la fonction xcorr pour le signal ecg3

![image](https://user-images.githubusercontent.com/79712514/215356089-ec5f1f2c-5d3d-4cb4-bb84-ad62f8839236.png)


On detecte une correlation dans un maximum a taux = 2

