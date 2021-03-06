vagrant-grunt-bower
===================

Vagrant configuration with grunt, bower, php, mysql included.

Prerequisites
=============
Please install 
- Vagrant: [http://www.vagrantup.com/downloads](http://www.vagrantup.com/downloads)
- VirtualBox: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

Installation
============

Clone this repository:
----------------------
````
git clone https://github.com/geomagilles/vagrant-grunt-bower.git
``````

Run vagrant:
------------
````
cd vagrant-grunt-bower
vagrant up
````
Have a coffee - At the end you could access a simple html page at [http://localhost:8080](http://localhost:8080)

Then enter the virtual machine and locally install bower components and whatever grunt plug-ins you want:
````
vagrant ssh
cd /vagrant/www
bower install
npm install grunt
npm install grunt-contrib-copy
npm install grunt-contrib-concat
npm install grunt-contrib-uglify
npm install grunt-contrib-watch
npm install grunt-contrib-cssmin
npm install grunt-contrib-imagemin
npm install grunt-phpunit
````
Grunt and Bower are now ready to be used.

Laravel New Install (optional):
------------------------------------
If you want a fresh install of Laravel, just enter the virtual machine (vagrant ssh), then
````
cd /vagrant
git clone --no-checkout https://github.com/laravel/laravel.git ./laravel
mv laravel/.git www/.
rmdir laravel
cd www
git reset --hard HEAD
rm public/index.html
composer install
````

Have a look at [http://localhost:8080](http://localhost:8080), you have arrived!
