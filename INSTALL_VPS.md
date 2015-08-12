# Install VPS #
<pre>
# install NODE<br>
wget http://nodejs.org/dist/v0.8.14/node-v0.8.14.tar.gz<br>
tar xvzf node-v0.8.14.tar.gz<br>
cd node-v0.8.14<br>
./configure<br>
make<br>
sudo make install<br>
cd ..<br>
sudo ln -s /usr/local/bin/node /usr/bin/node<br>
sudo ln -s /usr/local/lib/node /usr/lib/node<br>
sudo ln -s /usr/local/bin/npm /usr/bin/npm<br>
sudo ln -s /usr/local/bin/node-waf /usr/bin/node-waf<br>
sudo node -v<br>
# install JAP_REMOTE_NODE<br>
wget http://jap.googlecode.com/files/JAP_REMOTE_NODE-0.2.0.zip<br>
unzip JAP_REMOTE_NODE-0.2.0.zip<br>
cd JAP_REMOTE_NODE-0.2.0<br>
# generate certificate<br>
rm CAK.pem<br>
rm CA.pem<br>
rm CA.srl<br>
openssl genrsa -des3 -out CAK.pem 2048<br>
openssl req -new -x509 -days 3650 -key CAK.pem -out CA.pem -config CA.ini<br>
rm CK.pem<br>
rm CR.pem<br>
rm C.pem<br>
# configure C.ini<br>
nano C.ini<br>
openssl genrsa -out CK.pem 1024<br>
openssl req -new -key CK.pem -out CR.pem -config C.ini<br>
openssl x509 -req -in CR.pem -out C.pem -CA CA.pem -CAkey CAK.pem -CAcreateserial -days 3650 -extensions v3_req -extfile C.ini<br>
# configure JAP_REMOTE_NODE.json.js<br>
nano JAP_REMOTE_NODE.json.js<br>
# start JAP_REMOTE_NODE<br>
sudo nohup node JAP_REMOTE_NODE.js &<br>
# stop JAP_REMOTE_NODE<br>
# ps -ef<br>
# kill -9 <id><br>
</pre>