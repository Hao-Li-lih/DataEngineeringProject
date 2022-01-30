# DataEngineeringProject

   # *TOP50  Steam games*

Notre projet est un site de présentation des jeux du Top 50 de Steam basé sur Flask, Mongo et Scrapy.

Nous allons afficher un tableau dynamique des prix sur la page web, où vous pourrez voir le nombre de jeux avec des prix différents en pourcentage du nombre total de jeux.

Après cela, nous avons une brève description des trois meilleurs jeux. Comme certains jeux avec DLC sont comptabilisés comme un seul jeu, nous les avons regroupés pour établir le tableau, de sorte que le nombre final de jeux est inférieur à 50 car nous avons supprimé les doublons.

```
Étapes de la réalisation de notre projet:
   - Explorer les données via un crawler et sauvegarder les données dans un fichier au format json.这边还要补充一下文件夹的名字。 
   - Exécutez le fichier mongo.py dans "flasksteam" pour lire les données et les enregistrer dans MongoDB.
   -Exécutez app.py et ouvrez le site Web par défaut http://127.0.0.1:5000/ pour afficher notre site Web.
  
  ```

## Docker

## 1 Scrape




## 2 Mongo
- Nous enregistrons les données au format json, nommé "data5.json".
- Nous passons les données dans la base de données mongo via mongo.py. Le nom de la base de données est "Steamgame" et nous créons une collection appelée "steam". Le port est le port par défaut 27017.

```
client = MongoClient('mongodb://localhost:27017/')  
database = client['steamgame']  
collection = database['steam']
df_json=pd.read_json("data5.json")  
collection.insert_many(df_json.to_dict(orient='records'))
```


## 3 Flask

Nous utilisons Echarts et bootstrap pour concevoir notre page d'accueil. Les fichiers js et css des deux sont stockés dans le dossier "static"（flasksteam/static）.
Le fichier de mise en page de notre site web est "index.html", qui se trouve dans le dossier "tamplates".


## Contact

* **Hao LI** - *student* -ESIEE Paris，<hao.li@edu.esiee.fr>
* **Zhneyu ZHU** - *student* -ESIEE Paris，<zhenyu.zhu@edu.esiee.fr>
