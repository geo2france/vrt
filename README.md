# vrt
Liste des fichiers VRT en prod sur Géo2France

## Ressources frequemment utilisées pour rédiger les vrt :
* https://gdal.org/drivers/vector/vrt.html (documentation GDAL)
* https://geotribu.fr/articles/2021/2021-09-07_traiter_fichiers_adresse_gdal_csv_vrt/ (article geotribu)
* https://portailsig.org/content/ogr-que-la-force-soit-avec-les-formats-virtuels.html (article du Portail SIG)
* https://github.com/jeanpommier/ogr2vrt_simple (un outil de @jeanpommier qui génère un vrt à partir d'un jeu de donnée compatible OGR)

## Utilisation des fichiers vrt
* Une fois les fichiers vrt rédigés et testés dans QGIS, les jeux de donnée en entrée sont convertis en une table PostgreSQL via l'outil VRT-bot : https://github.com/georchestra/vrt-bot/tree/main disponible dans l'IDS georchestra.
* Ces tables sont ensuite publiées par geoserver pour produire des flux OGC interopérables, utilisables dans des visionneuse cartographiques, des tableaux de bord, etc
