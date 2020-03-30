#!/bin/bash
#get the data from the JHU dashboard and save into JHU_new.json
curl 'https://services1.arcgis.com/0MSEUqKaxRlEPj5g/ArcGIS/rest/services/ncov_cases/FeatureServer/1/query?f=json&where=Confirmed%3C%3E0&objectIds=&time=&geometry=&geometryType=esriGeometryEnvelope&inSR=&spatialRel=esriSpatialRelIntersects&resultType=none&distance=0.0&units=esriSRUnit_Meter&returnGeodetic=false&outFields=*&returnGeometry=false&featureEncoding=esriDefault&multipatchOption=none&maxAllowableOffset=&geometryPrecision=&outSR=&datumTransformation=&applyVCSProjection=false&returnIdsOnly=false&returnUniqueIdsOnly=false&returnCountOnly=false&returnExtentOnly=false&returnQueryGeometry=false&returnDistinctValues=false&cacheHint=true&orderByFields=&groupByFieldsForStatistics=&outStatistics=&having=&resultOffset=0&resultRecordCount=2000' -H 'Referer: https://gisanddata.maps.arcgis.com/apps/opsdashboard/index.html' -H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.149 Safari/537.36' -H 'Sec-Fetch-Dest: empty' --compressed >JHU_new.json

#filter the JSON to get the data we want
jq '.features' JHU_new.json > JHU_new2.json

#Convert it to newline delimiter JSON, if you are not loading the data into BigQuery, you can skip this step
cat JHU_new2.json | jq -c '.[]' > JHU_new3.json


