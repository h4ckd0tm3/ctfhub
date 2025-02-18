Place your TLS certificate + private key(s) for your domain here like

```
./<domain>/fullchain.pem
./<domain>/privkey.pem
```

Then edit `../nginx/nginx.conf` to update the path to the chain/key.

Note:
-----

For local development, you can use [mkcert](https://github.com/FiloSottile/mkcert) to generate the certificates.

Example with default settings working with the provided `nginx.conf`:


```
# If this is the first time you are using mkcert, create a local CA:
mkcert -install

# Generate a new certificates with the different subdomains:
mkcert ctfhub.mydomain.com hedgedoc.mydomain.com excalidraw.mydomain.com collab.excalidraw.mydomain.com

# Move the generated certificates to the certs folder. Assuming you are at the repository root folder:
mkdir -p ./conf/certs/ctfdad.mydomain.com
mv ctfhub.mydomain.com*-key.pem ./conf/certs/ctfdad.mydomain.com/privkey.pem
mv ctfhub.mydomain.com*.pem ./conf/certs/ctfdad.mydomain.com/fullchain.pem
```

If `ctfhub.mydomain.com` is in the `/etc/hosts` file of your machine, then go to `https://ctfhub.mydomain.com` and enjoy the app!
