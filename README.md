# solritas

## Example

    bin/solr start -c -Denable.packages=true
    bin/solr create -c my_data
    bin/post -c my_data -type text/csv -out yes -d $'id,title\n1,One\n2,Two\n3,Three\n4,Four\n5,Five\n6,Six\n7,Seven\n8,Eight\n9,Nine\n10,Ten'

    bin/solr package add-repo solritas https://raw.githubusercontent.com/erikhatcher/solritas/master/repo
    bin/solr package install solritas
    bin/solr package deploy -y solritas -collections my_data -p DF=title

    open http://localhost:8983/solr/my_data/browse

## Building a release

    openssl dgst -sha1 -sign <path-to-privatekey.pem> <new-jar-file> | openssl enc -base64

### Running repository locally

    cd repo
    python -m SimpleHTTPServer

Substitute `http://localhost:8000` for the repository URL: `bin/solr package add-repo solritas http://localhost:8000`

## TODO

copy/paste/adapt from Ishan's great https://github.com/chatman/question-answering README and example

