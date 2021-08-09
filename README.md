# standardSec

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/apache-selfsigned.key -out /etc/ssl/certs/apache-selfsigned.crt
openssl req -x509 -nodes -days 365 -newkey rsa:4096 -keyout /etc/ssl/private/apache-selfsigned.key -out /etc/ssl/certs/apache-selfsigned.crt -extensions mysection -config myconfig.cnf
openssl ca -policy policy_anything -config  -out windows_server.crt -extensions some_ext -extfile some_extensions.txt -infiles cert_request.csr
openssl req -x509 -newkey rsa:2048 -keyout /etc/ssl/private/apache-selfsigned.key -sha256 -nodes -days 365 -config req.cnf -out /etc/ssl/certs/apache-selfsigned.crt

