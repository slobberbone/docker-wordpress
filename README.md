docker-wordpress
================
[![](https://badge.imagelayers.io/centurylink/wordpress.svg)](https://imagelayers.io/?images=centurylink/wordpress:latest 'Get your own badge on imagelayers.io')
Out-of-the-box Wordpress docker image without MySQL

Expose /var/www/html volume and port 80

Usage
-----

To create the image `slobberbone/wordpress`, execute the following command on the slobberbone-docker-wordpress folder:

	docker build -t slobberbone/wordpress .

You can now push your new image to the registry:

	docker push slobberbone/wordpress


Running your Wordpress docker image
-----------------------------------
Start and pull if needed MySQL/MariaDB image:

docker run -d --name mysql-wordpress -e MYSQL_ROOT_PASSWORD=XXXXXXX -v //media/your_directory/mysql/:/var/lib/mysql mysql:latest

Start your image:

	docker run -d --name wordepress -p 80:80 --link mysql-wordpress:mysql -v /media/your_directory:/var/www/html -d wordpress slobberbone/wordpress 

Test your deployment:

	curl http://localhost/

You can now start configuring your Wordpress container!
