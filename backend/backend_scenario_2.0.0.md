# Backend Scenario 2.0.0

Le document suivant décrit les fonctions principales du serveur backend afin d'assurer le bon fonctionnement de l'application et ses fonctionnalités, à l'état d'avancement 2.0.0.

Le scenario 2.0.0 inclut tout ce qui a déjà été réalisé pour le scénario 1.0.0 et y ajoute la création et gestion des projets / lots / activités.
Les projets, les lots et les activités étant traités de la même manière, ils seront décrits en parallèle.

## Création d'un projet / lot / activité

|Bouton|Fonction|Description|Return|
|-|-|-|-|
|Add Project|`add_project(user_id,project_name,budget,id_responsable)`|Vérifie que l'utilisateur est un superviseur et récupère les paramètres du projet et vérification d'erreurs (Projet déjà existant, nomenclature non respectée...)|Projet créé dans la database|
|Add Lot|`add_lot(user_id,lot_name,budget,start_date,end_date,project_id,id_responsable)`|Vérifie que l'utilisateur est un superviseur ou resposnsable projet et récupère les paramètres du lot et vérification d'erreurs (Lot déjà existant, nomenclature non respectée...)|Lot créé dans la database|
|Add Activité|`add_activity(user_id,activity_name,budget,start_date,end_date,id_lot)`|Vérifie que l'utilisateur est un superviseur ou responsable projet ou responsable lot et récupère les paramètres de l'activité et vérification d'erreurs (Activité déjà existante, nomenclature non respectée...)|Activité créée dans la database|

## Édition d'un projet / lot / activité

|Bouton|Fonction|Description|Return|
|-|-|-|-|
|Modification Projet|`edit_project(id_projet,user_id,project_name,budget,id_responsable)`|Vérifie que le projet existe, vérifie que l'utilisateur a les permissions, vérifie que les modifications sont autorisées|Base de données mise à jour|
|Modification Lot|`edit_lot(id_lot,user_id,lot_name,budget,start_date,end_date,id_responsable)`|Vérifie que le lot existe, vérifie que l'utilisateur a les permissions, vérifie que les modifications sont autorisées|Base de données mise à jour|
|Modification Activité|`edit_activity(id_activity,user_id,activity_name,budget,start_date,end_date)`|Vérifie que l'activité existe, vérifie que l'utilisateur a les permissions, vérifie que les modifications sont autorisées|Base de données mise à jour|


## Suppression d'un projet / lot / activité

|Bouton|Fonction|Description|Return|
|-|-|-|-|
|Suppression de projet|`delete_project(id_project,user_id)`|Vérifie que le projet existe, que l'utilisateur a les permissions|Projet supprimé de la base de données|
|Suppression de lot|`delete_lot(id_lot,user_id)`|Vérifie que le lot existe, que l'utilisateur a les permissions|Lot supprimé de la base de données|
|Suppression d'activité|`delete_activity(id_activity,user_id)`|Vérifie que l'activité existe, que l'utilisateur a les permissions|Activité supprimée de la base de données|

## Récupération d'informations

|Fonction|Description|Return|
|-|-|-|
`get_projects(user_id)`||Informe frontend des projets accessibles à l'utilisateur|
|`get_lots(user_id,project_id)`|Vérifie que le projet existe|Informe frontend des lots accessibles à l'utilisateur|
|`get_activities(user_id,lot_id)`|Vérifie que le lot existe|Informe frontend des activités accessibles à l'utilisateur|




## Saisies périodiques

|Bouton|Fonction|Description|Return|
|-|-|-|-|
|Log Time|`log_time(activity_id,user_id,time)`|Ajoute du temps travaillé sur l'activité|Temps enregistré dans la base de données|

## Clôtures
|Bouton|Fonction|Description|Return|
|-|-|-|-|
|Close Project|`close_project(project_id,user_id)`|Vérifie que le projet existe, vérifie que l'utilisateur est un superviseur, clôture tous les lots du projet et le projet|Projet et lots clôturés dans la base de données|
|Close Lot|`close_lot(lot_id,user_id)`|Vérifie que le lot existe, vérifie que l'utilisateur a les permissions, désigne le lot comme clôturé|Lot clôturé dans la base de données|

|Bouton|Fonction|Description|Return|
|-|-|-|-|
|Assign manager|`assign_manager(user_id,manager_id)`|Assigne un manager à un employé|Ajout lien manager-employé|
|Unassign manager|`unassign_manager(user_id,manager_id)`|Supprime le lien entre un manager et un employé|Suppression lien manager-employé|