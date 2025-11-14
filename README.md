# Cartographie multimodale des altérations endothéliales et métaboliques cérébrales dans le contexte de l’insuffisance rénale chronique
## *Analyse connectomique par imagerie moléculaire*
![Python](https://img.shields.io/badge/python-3.13.5-blue.svg)
![Anaconda](https://img.shields.io/badge/anaconda-distribution-green.svg)
![Academic Year](https://img.shields.io/badge/année-2025--2026-orange.svg)
![University](https://img.shields.io/badge/university-Aix--Marseille-red.svg)

Ce dépôt contient le code Python utilisé pour le traitement, l’analyse statistique et la visualisation de données de neuroimagerie dans un modèle murin d’insuffisance rénale chronique. 
Il inclut le workflow complet de génération des figures et un rapport détaillé au format article. Le projet utilise des données issues d’imagerie 
moléculaire bimodale (SPECT/CT et TEP/CT) afin d’explorer les altérations endothéliales et métaboliques cérébrales. Développé dans le cadre du Master 2 Digital Solutions 
for Pharmaceutical Sciences (Aix-Marseille Université).

## À propos

### Contexte du projet
Ce travail s'inscrit dans la continuité des recherches menées dans le cadre de mon mémoire de Master de Recherches en Neurosciences, consacré à l'étude de l'impact de l'hypertension sur la perméabilité de la barrière hémato-encéphalique et les troubles cognitifs dans le contexte de l'insuffisance rénale chronique.

### Contexte scientifique
L'insuffisance rénale chronique (IRC) correspond à une altération progressive et irréversible de la fonction rénale, résultant d'une destruction graduelle du parenchyme rénal. 
Elle se traduit par une réduction durable du débit de filtration glomérulaire et par l'accumulation de métabolites azotés tels que l'urée, la créatinine et l'acide urique. 
Sa prévalence est estimée entre 10 et 13 % dans le monde (INSERM, 2017).
Au-delà de l'atteinte rénale, l'IRC s'accompagne de complications systémiques, notamment neurologiques. Les patients présentent une incidence accrue d'accidents vasculaires cérébraux 
ischémiques et une prévalence élevée de troubles cognitifs, estimée entre 10 et 40 % selon les études.

## Objectifs du projet
### Problématique scientifique
Plusieurs travaux ont mis en évidence des modifications cérébrales dans l'insuffisance rénale chronique, touchant certaines régions clés (matière grise, réseaux fonctionnels, 
connectivité, métabolisme). L'objectif de ce projet est de cartographier et quantifier ces altérations à travers des analyses statistiques et des visualisations connectomiques.
### Données analysées
Les données proviennent d'un projet de recherche préclinique en neuroimagerie réalisé dans le cadre de mon stage de Master en Neurosciences. Elles incluent les valeurs de captation (ID/g) 
mesurées chez des rats pour deux traceurs d'imagerie moléculaire :

- **⁹⁹ᵐTc-DTPA** : évaluation de la perméabilité de la barrière hémato-encéphalique
- **¹⁸F-FDG** : mesure du métabolisme cérébral du glucose
  
### Objectifs analytiques

- Produire des visualisations claires et des analyses statistiques robustes des patterns de corrélation entre régions cérébrales (ROI)
- Caractériser les réseaux de covariation pour la perméabilité de la BHE et le métabolisme glucidique
- Explorer les relations entre profils de covariation régionale et paramètres cliniques associés à l'IRC
- Identifier les variations significatives via des tests statistiques appropriés (Mann-Whitney, corrélations de Spearman, transformation de Fisher-z, corrections FDR)
- Comparer la topologie des réseaux cérébraux entre groupes contrôle et pathologique

## Prérequis
### Environnement
- **Python** : 3.13.5
- **Distribution** : Anaconda
- **IDE** : JupyterLab

### Librairies Python principales
```python
# Manipulation de données
pandas
numpy

# Analyses statistiques
scipy
statsmodels

# Visualisation
matplotlib
seaborn

# Paramétrage graphique
matplotlib.patheffects
matplotlib.cm
plt.rcParams (police Helvetica, export PDF optimisé)
```
### Dépendances détaillées
Les analyses utilisent les modules suivants :
- `pandas` : manipulation et structuration des données
- `numpy` : calculs numériques et matrices
- `scipy.stats` : tests statistiques (Mann-Whitney, Shapiro-Wilk, Spearman, Pearson, Fisher-z)
- `statsmodels` : correction FDR (Benjamini-Hochberg)
- `matplotlib` : génération de graphiques (boxplots, heatmaps, connectogrammes)
- `seaborn` : visualisations statistiques

## Installation
### Cloner le dépôt
```bash
git clone https://github.com/Lpayre-sudo/cerebral-network-ckd-project.git
cd cerebral-network-ckd-project
```
### Installer les dépendances
```bash
pip install pandas numpy scipy statsmodels matplotlib seaborn
```

Ou avec conda :
```bash
conda install pandas numpy scipy statsmodels matplotlib seaborn
```

### Lancer JupyterLab
```bash
jupyter lab
```
## Usage
### Structure du projet
Le dépôt contient un notebook Jupyter unique organisé en blocs thématiques, chacun correspondant à un type d'analyse ou de visualisation spécifique.

### Utilisation
1. **Ouvrir le notebook dans JupyterLab**
```bash
   jupyter lab
```
2. **Préparer les données**
   - Placer le fichier Excel contenant les données de captation dans le répertoire du projet
   - Dans le notebook, remplacer le nom du fichier par celui de vos données

3. **Exécuter les analyses**
   - Suivre l'ordre d'exécution des cellules
   - Chaque bloc est précédé d'un titre Markdown indiquant le type de test statistique ou de figure généré
   - Les principaux blocs incluent :
     - Statistiques descriptives
     - Tests de normalité (Shapiro-Wilk)
     - Visualisations exploratoires (boxplots, heatmaps)
     - Tests de Mann-Whitney
     - Standardisation par z-scores robustes
     - Matrices de corrélation (Spearman)
     - Analyses connectomiques
     - Transformation de Fisher-z

4. **Personnalisation**
   - Adapter les noms de régions cérébrales (ROI) selon vos données
   - Ajuster les seuils statistiques si nécessaire
     
## 📁 Structure du projet
```
.
├── script_python_PAYRE.ipynb          # Notebook Jupyter avec toutes les analyses
├── Rapport_resultats.pdf              # Rapport détaillé au format article scientifique
└── README.md                          # Ce fichier
```

### Description des fichiers

- **script_python_PAYRE.ipynb** : Notebook contenant l'ensemble des analyses statistiques et visualisations, organisé en blocs thématiques
- **Rapport_resultats.pdf** : Document complet incluant l'état de l'art, matériels et méthodes, résultats, discussion, conclusion et références bibliographiques

## Exemples de résultats

### Perméabilité de la barrière hémato-encéphalique (⁹⁹ᵐTc-DTPA)

#### Comparaison intergroupe par région

![Boxplots DTPA](DTPA_boxplot_CTRL_vs_ARD.png)

Les boxplots montrent une augmentation significative de la captation du DTPA dans toutes les régions cérébrales du groupe ARD, traduisant une altération généralisée de la perméabilité de la BHE.

#### Distribution régionale de la captation

![Heatmap DTPA](DTPA_heatmap_CTRL_vs_ARD.png)

La heatmap illustre le gradient de captation entre groupes : valeurs faibles et homogènes chez les contrôles (teintes violettes), élévation marquée et hétérogène chez les ARD (teintes orangées à jaunes).

### Métabolisme cérébral du glucose (¹⁸F-FDG)

#### Réseau de corrélation métabolique - Groupe contrôle

![Connectome FDG Contrôle](CTRL_FDG_zscores_corr_spearman_connectogram_thresh0_70.png)

Le connectome métabolique des animaux contrôles présente une organisation dense et hiérarchisée (densité : 87,5 %), avec plusieurs hubs métaboliques majeurs (thalamus-hypothalamus, tronc cérébral, substance blanche cérébelleuse).

#### Analyse différentielle des corrélations métaboliques

![Comparaison CTRL vs ARD FDG](comparison_CTRL_vs_ARD_FDG_connectogram.png)

L'analyse par transformation de Fisher-z révèle une augmentation significative des corrélations métaboliques dans le groupe ARD (40 connexions sur 120, soit 33,3 %). Les arcs bleus indiquent une hyperconnectivité diffuse, particulièrement prononcée au sein des régions corticales et de leurs connexions avec les structures sous-corticales.

### Principaux résultats

- **⁹⁹ᵐTc-DTPA** : Augmentation de captation (×3) et fragmentation du réseau de corrélation (densité : 98,3% → 35,8%)
- **¹⁸F-FDG** : Augmentation de captation (×1,45) et hyperconnectivité métabolique (densité : 87,5% → 100%)
- **Dissociation** : Profils opposés entre perméabilité vasculaire (fragmentation) et métabolisme (hyperintégration)
