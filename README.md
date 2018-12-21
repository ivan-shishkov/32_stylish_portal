# Shared CSS Library

This solution allows you to create a test bench for developing a new CSS library in the case when changes in CSS need to be tested simultaneously on several sites.

# How to Test

Install [nginx](http://nginx.org):

```bash

$ sudo apt-get update
$ sudo apt-get install nginx

```

And clone this repository:

```bash

$ git clone https://github.com/ivan-shishkov/32_stylish_portal.git
$ cd 32_stylish_portal/

```

Rename the original nginx configuration file:

```bash

$ sudo mv /etc/nginx/nginx.conf /etc/nginx/nginx.conf.backup

```

And create a symbolic link to the configuration file from the repository:

```bash

$ sudo ln -s /absolute/path/to/32_stylish_portal/nginx.conf /etc/nginx/nginx.conf

```

Open the **nginx.conf** file in a text editor and in the **alias** directives, specify the **absolute path** to the **style.css** file from the repository.

Reload the nginx configuration:

```bash

$ sudo service nginx restart

```

Open a web browser a go to [http://localhost:9001/](http://localhost:9001/) or [http://localhost:9002/](http://localhost:9002/). This will replace the original CSS file with the **styles.css** file from the repository.


# Project Goals

The code is written for educational purposes. Training course for web-developers - [DEVMAN.org](https://devman.org)
