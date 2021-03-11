## Download
git clone https://github.com/snt1986/custom-api.git custom_api

## Get an Entity
POST to url:
* /api/{entity_type}/get/{id}
* Body: 
  * Schema [mandatory]
the body have the Schema of the data that do yo need return:
```json
{
	"schema": {
	  "title": []
  }
}
```


```json
{ 
  "schema": {
    "title": [],
     "field_image":["large"]
    }
}      
```
```json
{ 
  "schema": {
    "title": [],
    "field_image":["large"],
    "field_media": {
      "field_media_image": ["large", "medium"]
    }
  }
}      
```

## Create an Entity
* /api/{entity_type}/create
* Body: 
  * Schema [mandatory]
```json
{ 
  "schema": {
    "title": []  
  },
  "title": "Hola mundo",
  "type": "article"
}      
```

## Update an Entity
* /api/{entity_type}/update/{id}
* Body: 
  * Schema [mandatory]
```json
{ 
  "schema": {
    "title": []  
  },
  "title": "Hola mundo",
}      
```

## Delete an Entity
* /api/{entity_type}/delete/{id}

## Implement View
* /api/{view_id}/view/{display}
* Params GET: 
  * current_page [optional]. The page of the pagination, the default value is 0
  * lang [optional]
* Body: 
  * Schema [mandatory]
  * Fiters [optional]
```json 
{
  "schema": {
  	"title": []  	
  },
  "title": "ad"
}
         
``` 

## Get node by alias
* /api/{entity_type}/alias
* Body: 
  * Schema [optional]
  * alias [mandatory]
```json 
{
  "schema": {
  	"title": []
  	
  },
  "alias": "/ad"
}
         
``` 
# Use the display configuration.

If you wish use the display configuration of the Drupal UI (display manager), in the request, instead especify the fields in the schema, you can spcify the display:
```javascript 
{
	"schema": {"display": "teaser"}	
}
``` 

# TODO:
* Menu Endpoint
* Multiple Field ER for load a View Inside a Node
  - View ID
  - Display ID
  - Visualizatión (display)
* Metatags Compatibility