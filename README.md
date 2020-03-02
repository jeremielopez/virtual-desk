# Virtual Desk
Un projet visant à créer un **environnement de travail en VR** pour toute personne cherchant une **productivité maximale**.

[Virtual Desk App](https://virtual-desk-dc535.web.app/)
![Demo Virtual Desk App](https://firebasestorage.googleapis.com/v0/b/virtual-desk-dc535.appspot.com/o/Virtual%20Desk%20PC.png?alt=media&token=94e87c1c-ab05-40cd-91c2-30d19ec3d8f4)
[Vidéo de démonstration](https://www.youtube.com/watch?v=7k0PvTGZUdE)

## Technologie
* [Angular](https://angular.io/)
* [A-Frame](https://aframe.io/)
* [WebRTC](https://webrtc.org/)
* [Firebase](https://firebase.google.com/)

## Sources
* [Tutoriel sur la mise en place d'un flux WebRTC](https://www.grafikart.fr/tutoriels/webrtc-864)
* [Modèles 3D pour l'environnement](https://poly.google.com/)
* [Component A-Frame pour la modification de l'environnement](https://github.com/supermedium/aframe-environment-component)
* [Component A-Frame pour controler n'importe quel controller VR](https://github.com/wmurphyrd/aframe-super-hands-component)

## Concept
Dans un premier temps j'ai initialisé un projet *Angular* sous sa version 9.00beta.v-0.2 pour avoir la capacité de build du nouveau compiler *Ivy*.
J'ai donc entamé l'importation de A-Frame et des différents components dont j'avais besoin.

### Problème n°1 - Importation des différents components
Certains des components n'ont pas étés mis à jour depuis la sortie de la V1 de A-Frame.
Depuis la V1, l'initialisation de A-Frame ne se fait qu'après l'initialisation du DOM, ce qui fait que certains components ne pouvaient être importaient directement à la chaine. C'est pourquoi j'ai du utilisé la librairie [Fetch Inject](https://github.com/englishextra/fetch-inject/), cette librairie m'a permis d'injecter les components une fois A-Frame intialisé dans la class Window.

Une fois ce problème reglé j'ai pu m'attelé à la réalisation d'une pièce pour échanger les données du PC vers la pièce VR.
Pour cela j'ai donc établi une conenxion WebRTC entre le device VR et le PC via un *échange d'offre et de réponses via une communication en temps réel avec Firestore*. **(voir tutoriel WebRTC)**

A partir de là j'ai donc un environnement avec un flux vidéo du PC dans l'environnement VR.
J'ai donc aussi rajouter la possiblité de gérer un son relaxant en 360°.

## Suite du projet
Malheureusement je n'ai pas pu terminer ce projet dans les temps (ce qui est normal en faite).
Mais je le continue dans l'optique de le proposer gratuitement à la communautée.

Voici une liste non-hexaustive des choses à faire encore dans ce projet :
* Etablir une connexion RDP dans WebRTC pour prendre le control du PC avec le controller VR
* Rendre possible le partage de pièce via un lien
* Ajouter un layout spherique pour la disposition des différents éléments ajoutable dans l'environnement
