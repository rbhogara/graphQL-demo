# graphQL-demo
This is a demo/selfpaced lab for graphql security talk at Krakow Offensive Security - Cisco


## Pre-Requisites
Docker 
Python

## Installing Vulnerable application
sudo docker pull dolevf/dvga
sudo docker run -t -p 5013:5013 -e WEB_HOST=0.0.0.0 dolevf/dvga

## Identifying and Fingerprinting 
graphw00f for finger printing graphql application - https://github.com/dolevf/graphw00f
python main.py -d -f -t http://<IP>:5013

Checking introspection - 
nmap nse for graphql introspection - https://github.com/dolevf/nmap-graphql-introspection-nse
nmap --script=graphql-introspection -sV 10.197.243.35 -p 5013

Run Introspection Query -
Altair GraphQL Client - https://altairgraphql.dev/#download (Browser extensions also available)
Introspection query - https://github.com/dolevf/Black-Hat-GraphQL/blob/master/queries/introspection_query.txt

This results would be in a pretty long response. Rather than review manually, let’s get a graphical representation with GraphQL Voyager.
GraphQL Voyager - https://graphql-kit.com/graphql-voyager/
(Change Scema > Introspection Query > Paste the result from the query above)
