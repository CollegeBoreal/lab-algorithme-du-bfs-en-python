{{ personne }} :tada: :tada: :tada: 

C'est ce que l'on appelle un parcours sans faute.

## Tracer la visite d'une personne

Il nous reste maintenant à rajouter un bout de code servant à optimiser l'algorithme.

Pour éviter les cycles ou des cycles partiels ou les etudiants seraient à proximité de plusieurs étudiants et que certains des étudiants ont déjà déjà répondu à la question si ils avaient un Mac. On va remédier à ce problème en tenant à jour une liste de personnes ayant répondus à la question ou ayant déjà été `visités`.

On tiendra une liste de personnes visitées en l'appellant `visitees`. On l'initialisera au préalable. Une liste vide peut s'écrire `list()` en Python mais on choisira son raccourci plus élégant `[]`. 

- [ ]   On placera ce code juste après l'appel de la fonction `search()`

```python
def search(name):
   visitees = []
```

```python
 def search(name):
+   visitees = []
    search_queue = deque()
    search_queue += eleves[name]
    while search_queue:
       personne = search_queue.popleft()
-      if personne_elue(personne):
-         print(personne + " a le fameux Mac")
-         return True
-      search_queue += eleves[personne]
+      if not personne in visitees:
+         if personne_elue(personne):
+            print(personne + " a le fameux Mac")
+            return True
+         search_queue += eleves[personne]
+         visitees.append(personne)
    return False
```

**Push your code** to GitHub to continue:
```
git add dice_roller.py
git commit -m "Tutorial complete"
git push
```
