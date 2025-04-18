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

	feat(expand): add support for environment variable expansion

#### 3. Refactorisation du code

	feat(expand): add support for environment variable expansion

#### 4. Changement de style

	feat(expand): add support for environment variable expansion

#### 5. Mise à jour de la documentation

	feat(expand): add support for environment variable expansion

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
