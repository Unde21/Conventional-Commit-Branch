# Conventional Commits

## Introduction

La spécification Conventional Commits est une convention légère appliquée aux messages de commit.
Elle fournit un ensemble de règles simples pour créer un historique de commit clair et explicite, ce qui facilite l’utilisation d’outils automatisés basés sur cet historique.

## Types de Commit

| **Type**    | **Description**                                                                 |
|-------------|---------------------------------------------------------------------------------|
| `feat:`     | Ajout d'une nouvelle fonctionnalité                                             |
| `fix:`      | Correction d'un bug                                                             |
| `docs:`     | Modifications de la documentation uniquement                                    |
| `style:`    | Changement de style (indentation, espaces, formatage) **sans impact fonctionnel**|
| `refactor:` | Refactorisation du code **sans ajout de fonctionnalité ni correction de bug**   |
| `perf:`     | Amélioration des performances                                                   |
| `test:`     | Ajout ou modification de tests                                                  |
| `chore:`    | Tâches diverses (build, dépendances, scripts...) **hors code applicatif**       |
| `ci:`       | Modifications liées à l'intégration continue (GitHub Actions, GitLab CI...)     |


## Structure du Message de Commit

Le message de commit doit suivre la structure suivante:

    <type>(<scope>): <description>
	- <type>: Le type du commit, choisi parmi ceux listés ci-dessus (ex. feat, fix, refactor, etc..).
	- <scope>: Optionnel. Le scope (portée) du commit, décrivant la partie du code concernee (par exemple parsing, exec, etc..).
	- <description>: Une brève description du changement. Elle doit être concise, au présent et sans ponctuation finale.

### Exemples:

#### 1. Ajout d'une fonctionnalité

	feat(expand): add support for environment variable expansion

#### 2. Correction de bug

	fix: correct parsing issue with double quotes

#### 3. Refactorisation du code

	refactor: improve argument parsing logic

#### 4. Changement de style

	style: norm init.c

#### 5. Mise à jour de la documentation

	docs: update README with usage instructions

#### 6. Ajout ou modification de test

	test: add unit tests for libft

#### 7. Tâches diverses

	chore: add Valgrind suppression file

#### 8. Modifications liées à l'intégration continue

	ci: add Github Actions workflow for C build

## Bonnes Pratiques
### 1. Soyez précis mais concis

Essayez d’être aussi précis que possible dans la description du commit tout en étant concis. Une bonne description doit permettre à une autre personne de comprendre rapidement ce que le commit change.
Exemple à éviter:

	fix: bug

Exemple à privilégier:

	fix(parser): fix crash when reading empty file

### 2. Utiliser des verbes à l'infinitif

Les messages doivent être rédigés de manière impérative, comme si vous donniez un ordre. Cela permet d’avoir des messages cohérents et uniformes.
Exemple:

	feat(parser): add command line argument handling

### 3. Limiter la longueur du message de commit

Essayez de ne pas dépasser 50 caractères pour la description principale du commit. Pour les descriptions plus détaillées, vous pouvez ajouter une ligne vide et continuer sous forme de paragraphe.

### 4. Exemple Complet

Un message de commit complet avec une description détaillée pourrait ressembler à ceci :

	fix(parser): handle quoted arguments correctly

	The parser failed to correctly process arguments enclosed in single and double quotes in the command line.
	This commit fixes the issue and adds tests to ensure quotes are handled as expected.
	Tested with the following cases:
	- 'argument with space'
	- "argument with space"

### 5. Conclusion

Respecter ces conventions garantit une meilleure lisibilité de l'historique des commits, ce qui facilite la gestion des versions et la collaboration au sein du projet.

# Conventional Branch

## Introduction

La convention de branche standardisée ("Conventional Branch") fait référence à une nomenclature structurée et cohérente des branches Git, visant à rendre leur nom plus lisible et explicite. Nous suggérons des préfixes de branches que vous pouvez utiliser, mais vous êtes libres de définir vos propres conventions.
Une convention cohérente facilite l’identification rapide du type de travail effectué sur chaque branche.


## Points clés

- Branches orientées objectif : Chaque nom de branche indique clairement son but, ce qui permet à tous les développeurs de comprendre facilement à quoi elle sert.
- Intégration CI/CD : Grâce à des noms de branches cohérents, les systèmes automatisés (comme les pipelines d’intégration/déploiement continu) peuvent déclencher des actions spécifiques selon le type de branche (ex : déploiement automatique depuis une branche release/).
- Collaboration en équipe : En rendant le but des branches explicite, cela facilite la collaboration, réduit les malentendus et permet de basculer facilement d'une tâche à une autre.

## Spécification

### Préfixes recommandés pour les branches

Les branches doivent être structurées comme suit :
	<type>/<description>


| **Type**    | **Utilisation**                                                                 |
|-------------|---------------------------------------------------------------------------------|
| `main`      | Branche principale de développement (main, master, ou devlop)                    |
| `feature/`  | Pour l'ajout de nouvelles fonctionnalités (ex: feature/add-login-page)           |
| `bugfix/`   | Pour la correction de bugs (ex: bugfix/fix-header-bug)                           |
| `hotfix/`   | Pour des correctifs urgents (ex: hotfix/security-patch)                          |
| `release/`  | Pour préparer une version (ex: release/v1.2.0)                                   |
| `chore`     | Pour des tâches non liées au code métier, comme les mises à jour de dépendances ou de documentation (ex: chore/update-dependencies)|


### Règles de base

- Minuscules et tirets uniquement: Utilisez uniquement des lettres minuscules (a-z), des chiffres (0-9) et des tirets (-) pour séparer les mots
Évitez les caractères spéciaux, les underscores (_) ou les espaces.
- Pas de tirets consécutifs ou finaux: Pas de double tiret (feature/new--login) ni de tiret à  la fin (feature/new-login-).
- Clair et concis: Le nom de la branche doit être descriptif mais court, indiquant clairement l’objectif.
- Inclure un numéro de ticket (si possible): Pour un meilleur suivi, ajoutew le numéro du ticket (ex: feature/issue-123-new-login).

### Conclusion

- Communication claire: Le nom de la branche permet à lui seul de comprendre l’objectif du changement.
- Compatible avec l’automatisation : Permet d'intégrer facilement des processus automatisés (différents workflows selon le type de branche).
- Évolutif : Convient parfaitement aux équipes de grande taille avec plusieurs développeurs travaillant sur des tâches variées.

En résumé, la convention conventional branch vise à améliorer l’organisation, la communication et l’automatisation dans les workflows Git.
