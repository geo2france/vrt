# vrt
Liste des fichiers VRT en prod sur Géo2France

## Ressources frequemment utilisées pour rédiger les vrt :
* https://gdal.org/drivers/vector/vrt.html (documentation GDAL)
* https://geotribu.fr/articles/2021/2021-09-07_traiter_fichiers_adresse_gdal_csv_vrt/ (article geotribu)
* https://portailsig.org/content/ogr-que-la-force-soit-avec-les-formats-virtuels.html (article du Portail SIG)
* https://github.com/jeanpommier/ogr2vrt_simple (un outil de [@jeanpommier]([https://www.github.com/jeanpommier) qui génère un vrt à partir d'un jeu de donnée compatible OGR)

## Utilisation des fichiers vrt
* Une fois les fichiers vrt rédigés et testés dans QGIS, les jeux de donnée en entrée sont convertis en une table PostgreSQL via l'outil VRT-bot : https://github.com/georchestra/vrt-bot/tree/main disponible dans l'IDS georchestra.
* Ces tables sont ensuite publiées par geoserver pour produire des flux OGC interopérables, utilisables dans des visionneuse cartographiques, des tableaux de bord, etc

  ## Description des VRT
  * [cartofriche_gpkg.vrt](cartofriche_gpkg.vrt) : récupère les données cartofriche sur data.gouv et filtre les données sur les 5 départements des Hauts-de-France
  * [irve_geojson.vrt](irve_geojson.vrt) : récupère les données des installations de recharge des véhicules éléctrique (IRVE) sur data.gouv et découpe les données géographiquement à la région Hauts-de-France
  * [bnlc_coiturage_pan.vrt](bnlc_coiturage_pan.vrt) : récupère les données des aires de covoiturage sur data.gouv
  * [dora.vrt](dora.vrt) : récupère les données des strucutres qui luttent contre l'illetrisme publiées sur la plateforme de l'inclusion (DORA dora.inclusion.beta.gouv.fr), filtre les données sur les 5 départements des Hauts-de-France, et renomme les champs en supprimant les caractères exotiques
  * [parcelle_forestiere.vrt](parcelle_forestiere.vrt) : récupère les délimitations des parcelles forestières sur un flux WFS, filtrés géographiquement sur l'emprise de la région Hauts-de-France.
  * [zonage_inventaire_inpn.vrt](zonage_inventaire_inpn.vrt) : regoupe plusieurs flux WFS en une seule couche en ajoutant un champ _type_ contenant le nom de la couche (=le type de protection) + filtre géographique sur l'emprise de la région Hauts-de-France.
  * [zonage_nat2000_inpn.vrt](zonage_nat2000_inpn.vrt) : regoupe plusieurs flux WFS en une seule couche en ajoutant un champ _type_ contenant le nom de la couche (=le type de protection) + filtre géographique sur l'emprise de la région Hauts-de-France.
  * [zonage_protection_inpn.vrt](zonage_protection_inpn.vrt) : regoupe plusieurs flux WFS en une seule couche en ajoutant un champ _type_ contenant le nom de la couche (=le type de protection) + filtre géographique sur l'emprise de la région Hauts-de-France.
  * [gpu_zonage.vrt](gpu_zonage.vrt) : données de zonage du [Géoportail de l'urbanisme](https://www.geoportail-urbanisme.gouv.fr/map), découpées sur l'emprise des Hauts-de-France.
