Continuons maintenant dans une recherche arborescente plus approfondie.

- [ ] Pour naviguer dans la queue, on va demander aux personnes de sortir par la gauche `(du bus)` et tant qu'il y a une personne dans la queue, on continue. Le mouvement s'arrete quand la queue est vide. Ceci est représenté par le code ci-dessous:

```python
    while search_queue:
       personne = search_queue.popleft()
```

Ce code ne fait que faire sortir les premières personnes entrées dans le bus. Le code ne tient pas compte des `autres stations de bus`, dans notre cas le lien de proximité de nos étudiants.

- [ ] Pour se faire, nous allons rajouter une ligne `search_queue += eleves[personne]` nous permettant de faire le lien entre tous les étudiants, remplir la queue au fur et à mesure et finalement `traverser` l'arbre entièrement.

```python
    while search_queue:
       personne = search_queue.popleft()
       search_queue += eleves[personne]
```

Ce code est finalement inutile car nous avons traversé l'arbre dans son entier sans avoir trouvé l'élu. Nous devons donc insérer la fonction définie plus tôt `personne_elue()` pour trouver au plus vite l'élu(e) et sortir de l'arbre. L'insertion de ce nouvel élément se fera juste à la sortie du bus `popleft()` et avant que la personne `rameute` ses amis `search_queue += eleves[personne]`.

- [ ] Sortir du bus, si la condition fait que on a trouvé notre bonheur, on sort du bus dans notre cas, on a trouvé la personne qui a un Mac en rajoutant le code suivant.

```python
   if personne_elue(personne):
      print(personne + " a le fameux Mac")
      return True
   else:
```

:bulb: Le code final de notre algorithme devrait ressemblé à ceci:

```python
   while search_queue:
      personne = search_queue.popleft()
      if personne_elue(personne):
         print(personne + " a le fameux Mac")
         return True
      else:
         search_queue += eleves[personne]
```

- [ ] Exécute ton code et ajoute en commentaire l'impression que tu as obtenu. On passera ensuite au code suivant.
