

print:
	@for pem in *.pem; do \
		echo "Fingerprint for $${pem}" ; \
		for hash in sha1 sha256 sha512; do \
			openssl x509 -in $${pem} -fingerprint -noout -$${hash}; \
		done; \
		echo ""; \
	done

all:
	cp ~/data/src/MySelfCA/certificate/net.mhayashi1120.ca.* ./
	cp ~/data/src/MySelfCA/certificate/net.mhayashi1120.ica0001.* ./
	openssl x509 -in net.mhayashi1120.ca.pem -outform der -out net.mhayashi1120.ca.der
	openssl x509 -in net.mhayashi1120.ica0001.pem -outform der -out net.mhayashi1120.ica0001.der

