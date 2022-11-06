# python-strings-lists

## Consignes générales

La calculatrice postfix, en Python.

Pour le rendu, remplissez **uniquement les fonctions** dans les fichiers désignés, veillez bien à n'ajouter aucun autre code dans ces fichiers. Évaluez votre note en local de temps en temps (cf ci-dessous).

Pendant que vous préparez vos exercices, vous pouvez travailler dans un notebook, ou dans un fichier `essais.py` si vous le souhaitez, par exemple:

```python
from calculatrice import import postfix_eval 

print(postfix_eval("1 1 +"))
```

## Rendre votre travail

Quand le résultat pour un des exercices est satisfaisant, git add, git commit, git push:

```shell
$ git add calculatrice.py
$ # ajoutez aussi tout autre fichier que vous voulez committer
$ git commit --message "Calculatrice v1"
$ git push
```

Rendu **obligatoire**:

- Calculatrice (nombres entiers)

Rendus facultatifs:

- Calculatrice typée (pas de tests auto)

## Évaluer votre note en local

Vous pouvez évaluer votre note en local, avec:

```shell
$ python grader.py
```

Si les tests ne finissent jamais, appuyez sur `Ctrl + C` pour interrompre.

## Exercice - Calculatrice polonaise inversée (postfix)

(Rendez votre exercice en complétant le fichier `calculatrice.py`)

### Sur les nombres entiers

Une fonction `postfix_eval` prend en entrée une chaîne qui décrit une opération à faire sur des entiers, en utilisant **la notation polonaise postfixée**, où on écrit par exemple `10 20 +` pour ajouter 10 et 20 ; cette notation est aussi appelée la **notation polonaise inverse**.

Les opérandes sont tous des entiers ; on demande de supporter les 4 opérations `+` `-` `*` et `/` (division entière), la calculatrice ne manipule donc que des entiers.

Lorsque la chaine est mal formée, vous devez renvoyer une des trois chaines suivantes :

- `error-syntax` si on ne peut pas comprendre l'entrée,
- `error-empty-stack`, si on essaie de faire une opération mais que l'on n'a pas les deux opérandes nécessaires,
- `error-unfinished`, si on détecte des opérandes non utilisés.

Exemples:

- `20 40 + 10 *` → `600`
- `20 6 6 + /` → `1`
- `10 -3 /` → `-4`
- `10 +` → `"error-empty-stack"`
- `10 20 30 +` → `"error-unfinished"`
- `10 20 30 oops` → `"error-syntax"`

### Calculatrice "typée"

Un peu plus difficile.

Écrire une variante de `postfix_eval` qui accepte en deuxième argument un type de nombre parmi `int`, `float`, ou `Fraction`, de sorte que la calculette utilise ce type pour faire ses calculs.

Pour les fractions:

```python
from fractions import Fraction
```

Exemples:

- `postfix_eval_typed("20 40 + 10 *", int)` → `600`
- `postfix_eval_typed("20 40 + 10 *", float)` → `600.0`
- `postfix_eval_typed("1 2 /", Fraction)` → `Fraction(1, 2)`

**indice :** attention au cas de la division, qui doit se comporter selon le type comme une division entière (comme dans `postfix_eval`), ou comme une division usuelle si le type le permet.

## License

All exercises above are licensed _CC BY-NC-ND, Thierry Parmentelat_

- [Calculatruce](https://github.com/flotpython/course/blob/71e4a51e4832cc5e070b9a26bd3deedf576138a0/w6/w6-s9-x1b-postfix.md) (added examples)
