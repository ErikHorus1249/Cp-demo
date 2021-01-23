://docs.confluent.io/platform/current/_images/cp-demo-overview.jpg)
# Confluent Platform Demo (SSL customize)

## 1. Clone the [confluentinc/cp-demo GitHub repository](https://github.com/confluentinc/cp-demo): 

    git clone https://github.com/confluentinc/cp-demo
## 2. Modify the configuration file and change the parameters of the key and certificate

### a. Key and certificate
 - ## parameters:
	 - Country Name (2 letter code) [AU]:
	 - State or Province Name (full name) [Some-State]:
	   
	  - Locality Name (eg, city) []:
	   
	   - Organization Name (eg, company) [Internet Widgits Pty Ltd]:
	   
	   - Organizational Unit Name (eg, section) []:
	   
	   - Common Name (e.g. server FQDN or YOUR name) []:

	  
### Before 
> Generate CA key openssl req -new -x509 -keyout snakeoil-ca-1.key -out snakeoil-ca-1.crt -days 365 -subj
> '/CN=ca1.test.confluentdemo.io/OU=TEST/O=CONFLUENT/L=PaloAlto/ST=Ca/C=US'
> -passin pass:confluent -passout pass:confluent
> 
### After 
> Generate CA key openssl req -new -x509 -keyout snakeoil-ca-1.key -out snakeoil-ca-1.crt -days 30 -subj '/CN=ca1.test.confluentdemo.io/OU=TEST/O=AIS/L=hanoi/ST=hanoi/C=VN'
> -passin pass:aisresearch -passout pass:aisresearch

### Files :

> ../scripts/security/appSA.config
> ../scripts/security/cert-verify.config
> ../scripts/security/cer-clean.config 
> ...
> 

![](https://i.imgur.com/bXNfSC1.png)
### change the password for all configuration files

![](https://i.imgur.com/FqeLYem.png)
### Include : 

 1. docker-compose.yml 
 2. Dockerfile-confluenthub 
 3. Dockerfile-local
 
 ![](https://i.imgur.com/50Tyb4v.png)


