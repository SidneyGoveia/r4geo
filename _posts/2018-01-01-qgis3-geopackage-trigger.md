---
title: QGIS 3.x
category: QGIS
feature_image: "https://picsum.photos/5032/2920?image=976"
tag: QGIS, Geopackage, SQL
---
# Geopackage Triggers
```SQL
CREATE TRIGGER update_esn AFTER INSERT
ON addresses
BEGIN
update addresspoints set “esn” = (select esn from polygon where st_within(new.geom, geom));
END;
```
### Calculo de área automático em Spatialite e Virtual Layers no QGIS
```SQL
CREATE TRIGGER 'calcula_area_alterada' AFTER UPDATE ON "plantio" 
FOR EACH ROW BEGIN 
    UPDATE "plantio" SET "area" = st_area(NEW."geom")/10000 
    WHERE "pkuid" = NEW."pkuid"; 
END;

CREATE TRIGGER 'calcula_area_alterada' AFTER UPDATE ON "plantio" 
FOR EACH ROW 
    BEGIN UPDATE "plantio" SET "area" = st_area(NEW."geom")/10000 
    WHERE "pkuid" = NEW."pkuid";
END;
```

## Referências
- http://northredoubt.com/n/2012/10/19/spatialite-and-triggers-to-update-data
- https://pigrecoinfinito.wordpress.com/2017/12/17/spatialite-e-i-trigger-per-il-calcolo-automatico-della-lunghezza-di-una-strada
- http://millermountain.com/geospatialblog/2017/10/23/qgis-and-spatialite
- https://jacobsgisportfolio.wordpress.com/2017/10/24/spatialite-qgis-pack-a-punch-for-free
- https://www.northrivergeographic.com/archives/adding-triggers-to-geopackage
- http://lifeingis.com/adding-triggers-to-spatialite-databases-in-qgis
