# Standard open ssl extended key

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/apache-selfsigned.key -out /etc/ssl/certs/apache-selfsigned.crt
openssl req -x509 -nodes -days 365 -newkey rsa:4096 -keyout /etc/ssl/private/apache-selfsigned.key -out /etc/ssl/certs/apache-selfsigned.crt -extensions mysection -config myconfig.cnf
openssl ca -policy policy_anything -config  -out windows_server.crt -extensions some_ext -extfile some_extensions.txt -infiles cert_request.csr
openssl req -x509 -newkey rsa:2048 -keyout /etc/ssl/private/apache-selfsigned.key -sha256 -nodes -days 365 -config req.cnf -out /etc/ssl/certs/apache-selfsigned.crt

//file req.conf 
[req]
distinguished_name = req_distinguished_name
#req_extensions = v3_req
prompt = no
[req_distinguished_name]
C = country (US, IR ,...)
ST = ST
L = City  
O = Organization
OU = Develop
CN = SITE           
[v3_req]
keyUsage = keyEncipherment, dataEncipherment
extendedKeyUsage = serverAuth
subjectAltName = @alt_names
