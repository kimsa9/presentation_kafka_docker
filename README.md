# Hands-on kafka - Commandes utiles

- Dans un nouveau terminal, entrer dans le broker :

`docker exec -ti broker bash`

- Créer le topic :  
`kafka-topics --create --zookeeper zookeeper:2181 --topic test --partitions 2 --replication-factor 1`

- Démarrer le console Producer :
`kafka-console-producer --broker-list localhost:29092 --topic test`

- Insérer des messages
> bonjour
> kafka
> zookeeper

- Dans un nouveau terminal, entrer dans le broker :  
`docker exec -ti broker bash`

- Lancer le Consumer pour lire le topic depuis le début :  
`kafka-console-consumer --bootstrap-server localhost:29092 --topic test --from-beginning`

On a affiche bien les messages envoyés précédemment dans le Producer.

- Dans un nouveau terminal, entrer dans le broker :  
`docker exec -ti broker bash`

- Lancer un Consumer lié à un groupe pour lire le topic :  
`kafka-console-consumer --bootstrap-server localhost:29092 --topic test --group try`

- Faire la même chose dans un autre terminal

- Insérer des messages dans le console Producer et observer la répartition entre les Consumer du groupe try

- Lister les topics du cluster :  
`kafka-topics --zookeeper zookeeper-1:2181 --list`

- Afficher les détails de notre topic test :
`kafka-topics --zookeeper zookeeper-1:2181 --describe --topic test`


