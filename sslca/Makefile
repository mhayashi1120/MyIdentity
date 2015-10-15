

all:
	cp ~/data/src/MySelfCA/certificate/net.mhayashi1120.ca.* ./
	cp ~/data/src/MySelfCA/certificate/net.mhayashi1120.ica0001.* ./
	openssl x509 -in net.mhayashi1120.ca.pem -outform der -out net.mhayashi1120.ca.der
	openssl x509 -in net.mhayashi1120.ica0001.pem -outform der -out net.mhayashi1120.ica0001.der

