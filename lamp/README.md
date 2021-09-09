These playbooks will deploy a LAMP stack.

The site.yml file that runs all playbooks is created during the infrastructure deployment as it needs the name remote user from the vars.yml file.

It deploys Apache and php on the Web1 host, and mariadb on the db1 server.

It enables communcation between the two servers, and deploys a simple index.php page that queries the databases from the web site.
