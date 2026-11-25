## Hypotheses 
Nous pensons que la météo (température, pluie, neige, grêle et vent), la fréquentation des autres périodes/jours/heures et le remplissage on un effet sur le flux de passagers. 

## Choix et préparation avant modélisation
1. Ligne : *on étudie uniquement la ligne T1* ✅ 
    - On retire les colonnes inutiles ✅
2. Dates : 
    - *On enlève complètement la période COVID* : 2020-03-15 et après ✅
    - On groupe par ligne, par sens et par heures et on compte le flow ✅
    - On enlève les jours avec une valeur de flow abérante : flow = 0
    - On ajoute les créneaux absents s'il n'y a pas eu de validation pendant une heure à un arrêt par exemple. 
3. Ajout de colonnes : 
    - Colonnes de dates et heure : 
        - Jour de la semaine ✅
        - Mois ✅
        - Heure ✅
    - Colonnes "suplémentaires" :
        - Vacances 0/1 ✅
        - Work/Not work days 0/1 ✅
        - Peak hours (on se fixe 7h-9h et 17h-19h par ex) 0/1 ✅
4. On sépare le dataset en 2 selon les sens de circulation
5. On split les deux datasets en deux : 
    - le training set [[2019-11-01 ; 2019-12-25],[2020-01-06 ; 2020-02-09]]
     - le validation set [[2019-12-26 ; 2020-01-05],[2020-02-10 ; 2020-03-15]]  

Ici, on a donc 2 data sets : 1 par sens de circulation. Chaque dataset s'appelle : 
    **- df_tram_s0**
    **- df_tram_s1**

6. On prépare un dataset de la météo par heures, jours et mois pour pouvoir le caler sur nos données ✅
    - On peut garder uniquement la température et savoir s'il neige, pleut ou non (2/1/0) ✅   

Ici, on a donc un dataset supplémentaire avec toutes les dates et la météo qu'il a fait heure par heure. On l'appelle **df_weather_cleaned** par la suite.

67. On prépare une fonction qui nous renvoie en fonction du jour de la semaine et de l'heure le nombre de trams en circulation pour connaître la capacité max de nos rames (moyen de vérifier que le modèle dit pas n'importe quoi) et si le tram est bondé ou pas. 

On appelle cette fonction **Max_capacity**

À la fin on a donc 6 datasets de tram, 1 de météo et une fonction "remplissage de la ligne"

## Choix de modélisation 
- On s'attarde uniquement sur le T1
- On enlève la période COVID
- Le modèle est entraîné sur une période différente du test. Le choix des dates a été fait de tel sorte à ce qu'on ait une période de vacances dans les deux cas et en tout 80/20 (80 = training)
- On n'essaie pas de chercher exactement pourquoi les valeurs de flow sont abérantes, on les retire juste. 
- On sépare le data set en 2, en considérant que la ligne de tram est enfait 2 entités différentes. 