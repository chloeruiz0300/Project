## In the original data
- We have the flow for each station every 15 minutes for each day. 
- One station is counted as 2 stations, one for each direction of travel. 

So, **to prepare our data**, we need to 
1. take only the T1 rows
2. split the data set in 2, one for each direction of travel (we can regroup them later or keep a copy of the T1 only)
3. Extract days, months and hours in new columns to facilitate work. 
4. Group by day/hour/month according to what we found most useful. 

## Which features can we create and use
- Using previous hours : 
    - 15 minutes before, 30 minutes before, 1 hour before, 2 hours before
    - Peak hours, day of the week, work vs week-end days, day of the month, holidays 
    - Vehicule capacity, number of vehicules, crowding
    - Weather data (You can found them here : https://www.historique-meteo.net/france/lyonnais/lyon/)
    - Grèves et incidents 


## Data available elsewhere
|       Horaires de la ligne T1 TCL       | Premier départ | Dernier départ | Départs | Fréquence 7 h – 9 h |
|:---------------------------------------:|:--------------:|:--------------:|:-------:|:-------------------:|
| Direction IUT Feyssine (départ Debourg) |                |                |         |                     |
| Jour                                    | Premier départ | Dernier départ | Départs | Fréquence 7 h – 9 h |
| Lundi – vendredi                        | 04:40          | 00:35          | 173     | toutes les 6 min    |
| Samedi                                  | 04:40          | 00:35          | 144     | toutes les 10 min   |
| Dimanche et fêtes                       | 05:25          | 00:35          | 88      | toutes les 15 min   |
| Direction Debourg (départ IUT Feyssine) |                |                |         |                     |
| Jour                                    | Premier départ | Dernier départ | Départs | Fréquence 7 h – 9 h |
| Lundi – vendredi                        | 04:36          | 00:26          | 175     | toutes les 5 min    |
| Samedi                                  | 04:51          | 00:26          | 138     | toutes les 10 min   |
| Dimanche et fêtes                       | 05:20          | 00:26          | 88      | toutes les 15 min   |

Normalement, il y a actuellement une vingtaine de tram (23) en service. Sûrement moins en vrai. On peut mettre 272 personnes, dont 56 places assises max. 
La ligne est composée de 27 arrêts, pour 43 minutes pour faire toute la ligne. Dcp, il faut au minimum 8 trams par direction le matin entre 7h et 9h pour satisfaire le passage toutes les 6 minutes. 