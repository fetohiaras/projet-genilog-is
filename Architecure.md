# Architecture

## Étape 0  
Frontend requete au demarrage  
Backend envoie page de connexion


## Connexion

2 champs:  
- Email
- MDP

Requête:
- Frontend
	- Crypte email et MDP avec fonctions de hash
	- Envoie au Backend email et MDP cryptés
- Backend
	- Réception
	- Vérification chez la DB
- DB
	- Contiens email et MDP et bool de 1ere connexion en stock (cryptés)


Réponse:
- Contiens la page à afficher
	- Si MDP oublié
		- Page MDP oublié
	- Si 1ere connexion
		- Page 1ere connexion
	- Si OK
		- Page IHM
		- Données à afficher pour l'user (Projets accessibles, activités sur lesquelles il travaille)
	Si pas OK
		- Page de connexion + erreur msg


## MDP oublié

1 champ:
- mail

Requête:
- Frontend
	- mail (crypté si décryptable)
- Backend
	- Réception
	- Vérification chez la DB
- DB
	- Contiens le mail

Réponse:
- Backend
	- Créé un MDP générique
	- Demande à DB de le stocker et mettre le bool de 1ere connexion à false
	- Si OK envoie mail qui contient le MDP générique
- DB
	- Stocke nouveau MDP générique
	- Mets le bool de 1ere connexion à false


## 1ère connexion

2 champs:
- MDP
- Confirmer MDP

Requête
- Frontend
	- Vérifie égalité des 2 champs
	- Si OK, envoie au Backend
	- Si pas OK, display erreur msg
- Backend
	- Réception
	- Demande à DB de modifie le MDP
- DB
	- Stocke le nouveau MDP

Réponse:
- Backend
	- Envoie page de connexion à Frontend
