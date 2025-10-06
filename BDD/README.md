<div style="text-align: justify;">

# Bese de Données

---

#### Prénom NOM – Prénom NOM
> Léo     – Boutonnet  
> Nathan    – Groussard  
> Tarek      – Talsi  
---

## Introduction
Ce diagramme UML représente les relations entre les entités **Utilisateur**, **Activité**, **Lot**, et **Projet**. Voici une explication détaillée de chaque entité et de leurs relations.

---

## Entités

### 1. Utilisateur
   Attribut            | Type          | Description                                      |
 |---------------------|---------------|--------------------------------------------------|
 | id                  | int           | Identifiant unique de l'utilisateur.            |
 | super user          | bool          | Indique si l'utilisateur a des droits étendus. |
 | nom                 | string        | Nom de l'utilisateur.                           |
 | prénom              | string        | Prénom de l'utilisateur.                        |
 | id_metier           | int           | Identifiant du métier de l'utilisateur.         |
 | password_hashed     | string        | Mot de passe haché de l'utilisateur.             |
 | email               | string        | Adresse e-mail de l'utilisateur.                 |
 | 1ere_connexion      | bool          | Indique si c'est la première connexion.          |

---

### 2. Activité
 | Attribut            | Type          | Description                                      |
 |---------------------|---------------|--------------------------------------------------|
 | id                  | int           | Identifiant unique de l'activité.               |
 | nom                 | string        | Nom de l'activité.                               |
 | libellé             | string        | Description de l'activité.                       |
 | date de Début       | string        | Date de début de l'activité.                     |
 | date de fin         | string        | Date de fin de l'activité.                       |
 | id_lot              | int           | Identifiant du lot associé.                      |
 | clôturée            | bool          | Indique si l'activité est clôturée.             |
 | id_responsable      | int           | Identifiant du responsable de l'activité.       |

---

### 3. Lot
 | Attribut            | Type          | Description                                      |
 |---------------------|---------------|--------------------------------------------------|
 | id                  | int           | Identifiant unique du lot.                       |
 | nom                 | string        | Nom du lot.                                      |
 | date de Début       | string        | Date de début du lot.                            |
 | date de fin         | string        | Date de fin du lot.                              |
 | id_projet           | int           | Identifiant du projet associé.                  |
 | clôturé             | bool          | Indique si le lot est clôturé.                   |
 | id_responsable      | int           | Identifiant du responsable du lot.              |

---

### 4. Projet
 | Attribut            | Type          | Description                                      |
 |---------------------|---------------|--------------------------------------------------|
 | id                  | int           | Identifiant unique du projet.                    |
 | nom                 | string        | Nom du projet.                                   |
 | id_responsable      | int           | Identifiant du responsable du projet.           |

---

## Relations

### Utilisateur - Activité
- **Type de relation :** Un utilisateur peut être responsable d'une ou plusieurs activités.
- **Attributs de la relation :**
  - `id_user` : Identifiant de l'utilisateur.
  - `id_Activity` : Identifiant de l'activité.
  - `temps` : Temps alloué à l'activité.
  - `date` : Date de l'activité.
  - `responsable` : Indique si l'utilisateur est responsable de l'activité.

### Utilisateur - Lot
- **Type de relation :** Un utilisateur peut être responsable d'un ou plusieurs lots.

### Lot - Projet
- **Type de relation :** Un lot appartient à un projet.

### Lot - Activité
- **Type de relation :** Un lot contient une ou plusieurs activités.

---

## File Display
- **Description :** Le diagramme montre que l'entité **Utilisateur** est liée à une fonctionnalité appelée **File display**.

---

## Conclusion
Ce diagramme UML permet de visualiser les relations entre les utilisateurs, les activités, les lots et les projets. Chaque entité est définie par ses attributs et les relations entre elles sont clairement établies.

---

