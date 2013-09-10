Nginx Module Development
========================

sudo apt-get install libpcre3-dev

wget http://nginx.org/download/nginx-1.4.1.tar.gz
tar zxvf nginx-1.4.1.tar.gz
git clone https://github.com/netkiller/redis2-nginx-module.git
cd nginx-1.4.1 

./configure --prefix=/srv/nginx \
                --add-module=../redis2-nginx-module
 
make -j2
make install

-----
