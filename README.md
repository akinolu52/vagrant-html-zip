# vagrant-html-zip

pick a fedora image

`vagrant init jacobw/fedora35-arm64`

set the public and private network

set the ram size needed for the server

`vagrant up` : to install the image

`vagrant ssh` : to login

switch to root user

`sudo -i`

then install the following

`yum install unzip wget httpd vim -y` (-y is to automatically accept all)

start the httpd service

`systemctl start httpd`

enable autostart from boot-time for httpd

`systemctl enable httpd`

stop and disable firewall service

`systemctl stop firewalld`

`systemctl disable firewalld`

check your default httpd page using the public IP of the server - you can use the one from vagrant file

write some markup in index.html

`cd /var/www/html`

`vim index.html`

switch to edit using 'i' then <h1>Welcome Emmanuel!</h1>

exit `:wq`

check your website

switch to temp folder, download and unzip the zipped website

`cd /tmp`

`wget https://www.tooplate.com/zip-templates/2135_mini_finance.zip`

`unzip 2135_mini_finance.zip`

copy the unzipped file to /var/www/html

`cd 2135_mini_finance`

`cp -r * /var/www/html`

accept to auto-replace the previous index.html you created.

then check out the site

`exit` to leave root

power down vagrant to end

`vagrant halt`
