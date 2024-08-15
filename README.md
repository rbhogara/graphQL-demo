# graphQL-demo<br>
This is a demo/selfpaced lab for graphql security talk at Krakow Offensive Security - Cisco<br>
<br>

## Pre-Requisites<br>
Docker <br>
Python<br>

## Installing Vulnerable application<br>
sudo docker pull dolevf/dvga<br>
sudo docker run -t -p 5013:5013 -e WEB_HOST=0.0.0.0 dolevf/dvga<br>

## Identifying and Fingerprinting <br>
graphw00f for finger printing graphql application - https://github.com/dolevf/graphw00f<br>
python main.py -d -f -t http://<IP>:5013<br>

Checking introspection - <br>
nmap nse for graphql introspection - https://github.com/dolevf/nmap-graphql-introspection-nse<br>
nmap --script=graphql-introspection -sV 10.197.243.35 -p 5013<br>

Run Introspection Query -<br>
Altair GraphQL Client - https://altairgraphql.dev/#download (Browser extensions also available)<br>
Introspection query - https://github.com/dolevf/Black-Hat-GraphQL/blob/master/queries/introspection_query.txt<br>

This results would be in a pretty long response. Rather than review manually, let’s get a graphical representation with GraphQL Voyager.<br>
GraphQL Voyager - https://graphql-kit.com/graphql-voyager/<br>
(Change Scema > Introspection Query > Paste the result from the query above)<br>
