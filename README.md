# solritas

## Example

    bin/solr start -c -Denable.packages=true

    bin/solr package add-repo solritas https://raw.githubusercontent.com/erikhatcher/solritas/master/repo
    bin/solr package install solritas
    bin/solr create -c my_data
    bin/solr package deploy -y solritas -collections my_data

    bin/post -c my_data -type text/csv -out yes -d $'id,title\n1,VrW'

    open "http://localhost:8983/solr/my_data/browse?q=*:*"

## Building a release

    openssl dgst -sha1 -sign <path-to-privatekey.pem> <new-jar-file> | openssl enc -base64

## TODO

copy/paste/adapt from Ishan's great https://github.com/chatman/question-answering README and example

