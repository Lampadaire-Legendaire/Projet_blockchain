# final_project

Pour obtenir les bon fichiers, il faut récupérer le fichier final_project.zip et le déziper dans le dossier projects.
J'ai conscience que la pratique est assez douteux mais pour une raison qui me dépasse, le contenu de ce dossier refuse de l'envoyer après le git push
Les fichiers des smarts contract se trouvent alors dans  : \projects\final_project\smart_contracts\final_project

Dans ce dossier se trouvent le fichier contract.py contient tous les smarts contract,
ainsi que test_contract.py pour tester toutes les fonctions


Je n'ai pas réussi à utiliser le système avec ASA car je ne suis pas parvenu à faire fonctionner l'api

## Description du Projet
Ce projet consiste à créer un smart contract pour gérer des utilisateurs et des actifs sur la blockchain Algorand. Le contrat permet :
- L'enregistrement d'utilisateurs
- L'ajout de fonds
- L'achat, la vente et l'échange d'actifs
- Le retrait de fonds

Le tout est implémenté en Python avec une simulation de `BoxMap` pour la gestion des utilisateurs et des actifs.

---

## Fonctionnalités Implémentées

### 1. Enregistrement des Utilisateurs
- **Description** : Permet d'enregistrer de nouveaux utilisateurs avec un solde initial de 0.
- **Méthode** : `register(account: str, name: str)`
- **Exception** : Levée si l'utilisateur existe déjà.

### 2. Ajout de Fonds
- **Description** : Ajoute des fonds au compte d'un utilisateur existant.
- **Méthode** : `fund_account(account: str, amount: int)`
- **Exception** : Levée si l'utilisateur n'existe pas.

### 3. Création et Mise à Jour des Actifs
- **Description** : Crée ou met à jour un actif de jeu avec un prix défini.
- **Méthode** : `upsert_asset(asset_name: str, description: str, price: int)`
- **Exception** : Seul l'administrateur peut ajouter des actifs.

### 4. Achat d'Actifs
- **Description** : Permet à un utilisateur d'acheter un actif s'il dispose de fonds suffisants.
- **Méthode** : `buy_asset(account: str, asset_name: str)`
- **Exception** : Levée si l'utilisateur ou l'actif n'existe pas ou si les fonds sont insuffisants.

### 5. Vente d'Actifs
- **Description** : Un utilisateur peut vendre un actif qu'il possède.
- **Méthode** : `sell_asset(account: str, asset_name: str)`
- **Exception** : Levée si l'utilisateur ne possède pas l'actif.

### 6. Échange d'Actifs entre Utilisateurs
- **Description** : Permet à deux utilisateurs d'échanger des actifs.
- **Méthode** : `trade_assets(sender: str, receiver: str, asset_name: str)`
- **Exception** : Levée si l'expéditeur ne possède pas l'actif à échanger.

### 7. Retrait de Fonds
- **Description** : Permet à un utilisateur de retirer des fonds de son compte.
- **Méthode** : `withdraw_funds(account: str, amount: int)`
- **Exception** : Levée si le solde est insuffisant.

---

## Tests Unitaires
Des tests unitaires ont été ajoutés pour valider chaque fonction du contrat.
- **Fichier des tests** : `test_contract.py`
python test_contract.py

