
# TP Cascade de Haar

> [!CAUTION]
> Les cascades de HAAR ne sont plus trop utilisés donc plus simple a mettre en ouevre avec un ancien opencv , par exemple pip install opencv-python==4.10.0.84 . 

**Prérequis**: connaissances à minima du traitement d'images. Bases d'algorithmie. Connaissances à minima de python. Manipulation des concepts de ROS.

Prise en main d'une librairie d'analyse d'images (OpenCV) et d'une cascade de Haar associée à la détection de visage.

OpenCV est la solution la plus utilisée pour le traitement d'images. Il s'agit d'un framework C++ pour lequel il existe un wrapper python. Une perte en performance peut être constatée (qui peut être en partie comblée par la compréhension et la mise en place de parallélisation ou l'usage des cartes graphiques comme support d’exécution). Dans le cadre de cette série de TP, l'accent n'est pas mis sur les performances mais le prototypage.

#### 1) Prendre en main le code suivant
[face_detection_test.py](cascade_haar/face_detection_test.py)

```python
import cv2
import sys

# Get user supplied values
imagePath = sys.argv[1]
cascPath = sys.argv[2]

# Create the haar cascade
faceCascade = cv2.CascadeClassifier(cascPath)

# Read the image
image = cv2.imread(imagePath)
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Detect faces in the image
faces = faceCascade.detectMultiScale(
    gray,
    scaleFactor=1.1,
    minNeighbors=5,
    minSize=(30, 30),
)

print("Found {0} faces!".format(len(faces)))
i=0
# Draw a rectangle around the faces
for (x, y, w, h) in faces:
    i=i+1
    cv2.rectangle(image, (x, y), (x+w, y+h), (27*i%256, 255-27*i%256, 27*i%256), 2)

cv2.imshow("Faces found", image)
cv2.waitKey(0)
```

Tester sur une dizaine d'images trouvées sur Internet, de tailles et de complexité différentes (au moins 2 images contenant des choses qui ressemblent à un visage humain pour nous mais qui ne le sont pas). Chercher aussi à trouver les limites de reconnaissance en fonction de la vue (face, profil, contre-plongée...).

Faites des essais, faites varier les paramètres existants dans le code. Faites générer à votre code un retour de log, le plus clair possible.

**Expliquer** comment fonctionne en détail ce code. Expliquer le principe des cascades de Haar appliqué à cet exemple.

Dans votre rapport, on doit voir:
- Une explication des cascades de Haar.
- Une explication du code et du fichier de configuration associés.
- Les exemples et les différents paramètres associés (plusieurs configurations pour chaque exemple avec une explication).

**Biblio complémentaires à consulter**:
- [https://realpython.com/blog/python/face-recognition-with-python/](https://realpython.com/blog/python/face-recognition-with-python/)
- [https://www.bogotobogo.com/python/OpenCV_Python/python_opencv3_Image_Object_Detection_Face_Detection_Haar_Cascade_Classifiers.php](https://www.bogotobogo.com/python/OpenCV_Python/python_opencv3_Image_Object_Detection_Face_Detection_Haar_Cascade_Classifiers.php)
- [https://docs.opencv.org/3.1.0/d7/d8b/tutorial_py_face_detection.html#gsc.tab=0](https://docs.opencv.org/3.1.0/d7/d8b/tutorial_py_face_detection.html#gsc.tab=0)

#### 2) Prise en main des traitements en temps réel, mise en œuvre de la webcam sous OpenCV

Mise en œuvre de la détection de visage au travers de la webcam. Prenez en main le code décrit dans l'article suivant:
- [https://realpython.com/blog/python/face-detection-in-python-using-a-webcam/](https://www.geeksforgeeks.org/python/face-detection-using-python-and-opencv-with-webcam/)](https://www.geeksforgeeks.org/python/face-detection-using-python-and-opencv-with-webcam/)


Faites différents tests et illustrez votre rapport avec vos conclusions (présence de personnes, conditions d'éclairage, influence des paramètres...).
Écrivez un code qui sauvegarde dans un répertoire visage, une image croppée du visage avec comme nom du fichier : `date_de_detection_numero.jpg` (numéro si plusieurs détectés sur l’image de 1 à N).  
Vous ferez un choix concernant le format de la “date de détection”. Tester sur un flux video .

##### Quelques infos

Prise en main de la caméra (utiliser plutôt les petites Logitechs).  
Brancher la caméra, prise en main de l'outil Linux `cheese` (ne marche pas sur toutes les caméras). Faites des photos de vous et de vos collègues. Testez ces photos avec le code précédent et différents paramètres.  
Joindre ces photos au rapport avec les détections associées et les paramètres utilisés.  
Comment choisir, si on branche 2 caméras, la source du flux?

La détection de visage est l'un des exemples de cascades de Haar implémentés sous OpenCV. Il en existe d'autres sur le site d'OpenCV:  
- [https://github.com/opencv/opencv/tree/master/data/haarcascades](https://github.com/opencv/opencv/tree/master/data/haarcascades)  
- ou lié à des projets open-source divers (exemple: [https://github.com/mrnugget/opencv-haar-classifier-training/tree/master/trained_classifiers](https://github.com/mrnugget/opencv-haar-classifier-training/tree/master/trained_classifiers)).


#### 3) Dépendances logicielles et matérielles, 
Définir les dépendances logicielles et matérielles , estimation des temps de réponses en fonctions des puissance de calcul

#### 4) POUR INFORMATION UNIQUEMENT, Création d'un classifieur (les cascades de haar ne sont plus utilisé de nos jours et la face d'apprentissage se révélait capricieuse)

L'idée est de mettre en place votre propre classifieur en vous basant sur le tutoriel et les codes suivants:
- [https://github.com/mrnugget/opencv-haar-classifier-training](https://github.com/mrnugget/opencv-haar-classifier-training)

Des informations complémentaires peuvent être trouvées sur les sites suivants:  
- Haar cascade, learning:
  - [https://memememememememe.me/post/training-haar-cascades/](https://memememememememe.me/post/training-haar-cascades/)
  - [https://coding-robin.de/2013/07/22/train-your-own-opencv-haar-classifier.html](https://coding-robin.de/2013/07/22/train-your-own-opencv-haar-classifier.html)

Votre objectif est de créer votre propre classifieur.  
Choisissez un objet/animal ou autre.  
Préparez vos images positives (http://www.image-net.org/) (la commande `wget` peut être utile une fois récupérée une liste d'URL).  
Détourez vos images avec Gimp (j'ai déposé mon dataset d'exemples sur les bananes).  
Essayez d'appliquer la procédure en essayant de donner du sens à chaque étape et de comprendre les différents et nombreux paramètres.

Je vous propose un ensemble d'images négatives sur le e-campus mais libre à vous d'en récupérer d'autres.

Le temps de calcul risque d'être de plusieurs heures/jours, nous verrons dans un second temps comment mener à terme votre apprentissage sur une autre machine. L'important est ici surtout de comprendre le processus d'apprentissage et sa mise en place.

On peut appeler plusieurs classifieurs en parallèle, soit sur l'ensemble de l'image, soit sur une portion (par exemple chercher des yeux dans un visage précédemment trouvé).



