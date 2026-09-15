# TP introduction

La vision par ordinateur pour un robot est cruciale pour permettre à la machine d’interagir intelligemment avec son environnement. Les besoins en vision varient selon les types de robots (robots de service, robots industriels, drones, véhicules autonomes, etc.) et leurs applications spécifiques (navigation, manipulation d’objets, surveillance, etc.). Voici une longue liste des principaux besoins en vision pour un robot :

Compléter/réorganiser cette liste si nécessaire. Trouver des exemples  en python d'outils/librairies permettant de répondre à ces besoins , mettre les liens et une illustration pertinente en fonctionnement. Indiquer la taille de la solution , les dépendances 
 logicielles, le format d'entrée et les format de sorties ainsi qu'une estimation des temps de traitements/puissance de calcul. 

 > [!IMPORTANT]
> Ce travail pourrait se révelait très long. On proposera un  tableau de solutions existantes pour les items  2,5,7,8,9,11,13,14. On ne se limitera à utiliser une  IA pour generer le tableau  sans vérification des sites de references à ajouter dans votre tableau).  Vous développerez à part du tableau a minima 3 solutions . L'idéal est pour ces solutions d'avoir tester s avec un exemple qui n'est pas celui de base associé à la solution. On captera  ces solutions en terme d'adaptations ,de qualité de fonctionnement , d'usage de ressource CPU/GPU/mémoire. On essayera d'expliciter la complexité quand cela a du sens ou d'évaluer les temps de réponses

### 1. **Détection d’objets et de personnes**
   - **Détection d’objets** : Identifier et localiser des objets dans l’environnement (ex. bouteilles, outils, meubles, etc.).
   - **Détection de personnes** : Reconnaître les êtres humains dans les scènes pour des interactions ou la sécurité.
   - **Reconnaissance faciale** : Identifier et distinguer les visages des personnes.
   - **Détection de véhicules** : Identifier les voitures, motos, camions, etc., dans un environnement extérieur.


### 2. **Suivi d’objets et de personnes**
   - **Suivi d’objets en mouvement** : Suivre la trajectoire d'un objet dans une séquence vidéo.
   - **Suivi de personnes** : Maintenir une personne dans le cadre pour un robot assistant ou un robot de surveillance.
   - **Multi-object tracking** : Suivre plusieurs objets simultanément (ex. dans un entrepôt ou une foule).

### 3. **Segmentation d’objets**
   - **Segmentation d'objets** : Séparer les objets du fond dans une image (utilisé dans la manipulation robotique ou la navigation).
   - **Segmentation sémantique** : Assigner un label à chaque pixel d’une image pour comprendre les limites exactes des objets.
   - **Segmentation instance** : Différencier plusieurs instances du même type d’objet (ex. deux chaises différentes dans une pièce).

### 4. **Reconstruction 3D et perception de la profondeur**
   - **Stéréovision** : Utiliser deux caméras 2D pour percevoir la profondeur et reconstruire des scènes en 3D.
   - **Depth Camera** : Utilisation de camera 3D (ToF , structured Light, LiDAR)

### 5. **Navigation visuelle**
   - **Reconnaissance de l'environnement** : Identifier les obstacles et les zones dégagées pour la navigation.
   - **Suivi de ligne** : Suivre une ligne tracée au sol, souvent utilisé dans les robots industriels ou éducatifs.

### 6. **Manipulation d’objets**
   - **Préhension d’objets** : Détecter, localiser et saisir des objets avec précision (robots industriels ou de service).
   - **Estimation de la pose d’objets** : Détecter l’orientation et la position exacte d’un objet pour une prise efficace.
   - **Manipulation de petits objets** : Nécessite une vision précise pour manipuler des objets de petite taille ou fragiles (robotique chirurgicale, robotique de précision).

### 7. **Reconnaissance d'activités et de gestes**
   - **Reconnaissance d'actions humaines** : Comprendre ce que fait une personne (ex. marcher, courir, s’asseoir).
   - **Reconnaissance de gestes** : Détecter et interpréter les gestes humains pour une interaction homme-machine naturelle.
   - **Détection des postures** : Comprendre la position du corps humain (assis, debout, couché) pour des interactions sécurisées.

### 8. **Lecture et interprétation de textes et de symboles**
   - **Reconnaissance de texte (OCR)** : Lire du texte sur des objets ou des panneaux pour comprendre l’environnement (ex. lecture d’étiquettes, de panneaux de signalisation).
   - **Reconnaissance de codes-barres et QR codes** : Scanner et interpréter des informations codées dans des environnements industriels ou commerciaux.
   - **Interprétation de panneaux de signalisation** : Pour les robots de navigation extérieure (drones ou véhicules autonomes).

### 9. **Reconnaissance de scènes et de contextes**
   - **Compréhension de scènes complexes** : Identifier la nature globale d'une scène (ex. cuisine, bureau, rue) pour ajuster le comportement du robot.
   - **Contextualisation** : Relier les objets entre eux pour comprendre leur rôle dans une scène (ex. table, chaise, assiette dans une scène de salle à manger).


### 10. **Détection d’anomalies et de défauts**
   - **Détection d'anomalies visuelles** : Identifier des anomalies ou des défauts sur des objets ou des machines (utilisé dans la robotique industrielle pour le contrôle qualité).
   - **Surveillance visuelle** : Détecter des comportements ou des événements anormaux pour la sécurité (robots de surveillance).


### 11. **Reconnaissance et suivi de visages**
   - **Reconnaissance de visages** : Pour identifier et suivre des personnes spécifiques.
   - **Suivi de l’attention** : Suivre les mouvements des yeux et la direction du regard d’une personne pour interpréter l’intention.

### 12. **Analyse de la qualité des produits**
   - **Inspection industrielle** : Utiliser la vision pour contrôler la qualité des produits dans une chaîne de production (détection de défauts, d’usure ou d’anomalies).
   - **Comptage d’objets** : Estimer le nombre d’objets dans une scène pour des tâches de gestion ou d’automatisation.

### 13. **Interaction homme-machine améliorée**
   - **Suivi des expressions faciales** : Détecter et analyser les émotions humaines à partir des expressions du visage pour améliorer l’interaction homme-robot.
   - **Interaction vocale basée sur la vision** : Utiliser la vision pour améliorer la reconnaissance vocale (en identifiant les personnes qui parlent par leurs mouvements de bouche).

### 14. **D'autres idées ... ???**





