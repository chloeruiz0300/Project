# READ ME
## Structure of the project :
project/
├── data/ data
│ ├── raw/ never modified
│ └── processed/
├── notebooks/ notebooks │ ├── 01_exploration.ipynb
│ ├── 02_preprocessing.ipynb
│ └── 03_training.ipynb
├── src/ functions │ ├── __init__.py
│ ├── utils.py
│ └── student.py
├── results/ outputs ├── .venv/ not versioned
├── config.yaml
├── requirements.txt ├── .gitignore
└── README.md

## Things to do :   
 - Data Exploration av 20/11 
    - Explication des valeurs incohérentes #Maxime
 - Data preparation av 20/11
    - Vérification des données #Maxime
    - Compréhension des ≠ colonnes #Maxime #Baptiste DONE
    - Réflexion sur la méthode de travail : #Baptiste
        - Training, testing and forecasting 
        - Features => flux horaire(/jour) DONE
        - Explicitation des hypothèses DONE
 - Regressions av 27/11
    - Clean le truc #Baptiste (si tps)
    - Reprendre les bonnes features pr la regression
    - Tester plusieurs regressions et l'améliorer au fur et à mesure
    - Plotting tt 
    - Testing des modèles
    - Forecasting des modèles
 - Rédaction du rapport + support de présentation av 3/12 #Chloé

## Sections du rapport 
- Context and question, Problem, goals and why they matter, 1-2 pages
- Data and assumptions, Coverage, quality issues and limitations, 1-2 pages
- Preparation and features, Cleaning choices and feature construction, 2-4 pages
- Analysis and ML methods, Methods, baseline and evaluation approach, 2-4 pages
- Results and conclusions, Evidence, interpretation, limits and next steps, 4-10 pages