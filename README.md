# MocanaLighthouseSampleServer
This is a sample NodeJS project that will help test the Mocana Lighthouse SDK. Its a self contained Node JS app that uses Express to run the webserver as well as a few other handy node modules to make things pretty. The Node HTTPS library is pretty robust and is the only thing doing the checking on the certs, including parsing out the subject name.

The default SSL certificate for the server is for
lighthouse.demo.local

Since I run this locally for testing, I simply added an entry in my hostsfile for
127.0.0.1    lighthouse.demo.local

The HTTPS server is running on port 8443

So simply browse to and you should be prompted for a certificate.
https://lighthouse.demo.local:8443

You'll need a client certificate from Mocana's demo CA. You can always use your own CA to issue certs as well, but it will of course require changing out the ca.crt file with the certificate from your issuing authority. In fact if you want to change the whole thing out, here are the files and what they do:

/ssl/ca/ca.crt
  This contains the certificate of the issuing authority of the client certificate. 

/ssl/server/certificates/server.crt
  This is the certificate for the server - and currently has the subject of lighthouse.demo.local

/ssl/server/keys/server.key
  This is the private key for the server - and what was used for the certificate.

