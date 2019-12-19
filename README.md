# solritas

## Example

    bin/solr start -c -Denable.packages=true

    bin/solr package add-repo solritas https://raw.githubusercontent.com/erikhatcher/solritas/master/repo
    bin/solr package install solritas
    bin/solr create -c my_data
    bin/solr package deploy -y solritas -collections my_data

Add `&wt=solritas&layout=layout` to any search request to get results rendered as HTML search results.

Add a `/browse` handler:

  curl -X POST -H 'Content-type:application/json' -d '{
    "add-requesthandler": {
      "name": "/browse",
      "class": "solr.SearchHandler",
      "defaults": { "wt": "solritas" ,"v.layout": "layout", "v.template": "browse" },
      "useParams": "x"
    }
  }' http://localhost:8983/api/collections/my_data/config


*TODO* copy/paste/adapt from Ishan's great https://github.com/chatman/question-answering README and example

## Building a release

    openssl dgst -sha1 -sign <path-to-privatekey.pem> <new-jar-file> | openssl enc -base64
