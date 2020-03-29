## Utilisation de Variables

Pour faire une recherche arborescente, il nous faut un arbre.

Dans cet exemple, on va créer un arbre que l'on appellera `élèves` qui nous permettra de naviguer à travers une classe d'étudiants. Ces étudiants ont comme relation, une relation de proximité.

La(e) premièr.e étudiant(e) assit au bout d'une table forme le groupe de l'étudiant(e) de cette table. L'étudiant(e) assis(e) à l'autre bout de table est forcément à proximité d'un(e) étudiant(e) d'une autre table.

La relation de proximité ne peux former de boucle afin de respecter la description d'un arbre [voir DAG](https://en.wikipedia.org/wiki/Directed_acyclic_graph)

```python
eleves = {}
eleves["Boris"]=["Amir","Franck","Nathalie","Bertrand"]
eleves["Amir"]=[]
eleves["Franck"]=[]
eleves["Nathalie"]=[]
eleves["Bertrand"]=["Erna","Hassana","Abdelkrim"]
eleves["Erna"]=[]
eleves["Hassana"]=[]
eleves["Zoureni"]=["Sekou","Auriane","Corlings"]
eleves["Sekou"]=[]
eleves["Auriane"]=[]
eleves["Corlings"]=[]
eleves["Abdelkrim"]=["Souleyman","Zack","Zoureni"]
eleves["Souleyman"]=[]
eleves["Zack"]=[]
```

```python
def search(name):
   print( len(eleves.values()) )
   return False

if __name__== "__main__":
   search("Boris")
```

Now run the code and put *the number* you rolled as a comment, and then we'll keep this tutorial *rolling*!