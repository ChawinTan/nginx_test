## Simple nginx with node server setup

A simple barebones set up with nodejs express server with an nginx proxy on your localhost. This setup is done on ubuntu 18.04 and node node v14.15.1

### Instructions

1) clone this repo, `cd` into the root directory and `npm install`.
2) Install nginx. `sudo apt update` followed by `sudo apt install nginx`.
3) navigate to `etc/nginx/sites_enabled` and create a new sites_enabled for this app. Let's call it `nginx_test`. Run the command `sudo touch nginx_test` to create the file.
4) copy the contents in the file `nginx_sites_enabled_file` from the app root directory into the `nginx_test` file.
5) Run `sudo systemctl restart nginx` to see the changes.
6) Test if a symlink is created from sites-available to sites-enabled. Run `sudo nginx -t`. If all is right, it should something like this:

```
configuration file /etc/nginx/nginx.conf test is successful
```
7) If not, run `sudo ln -s /etc/nginx/sites-available/nginx_test /etc/nginx/sites-enabled/` and repeat step 6 to test again
8) Go to `localhost:80/hello` and you should see `Hello World` in h1 font

