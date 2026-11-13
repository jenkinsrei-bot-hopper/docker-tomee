FROM ibm-semeru-runtimes:open-21-jre-jammy

ENV PATH=/usr/local/tomee/bin:$PATH
RUN mkdir -p /usr/local/tomee ~/.gnupg

WORKDIR /usr/local/tomee

RUN apt-get update \
  && apt-get install -y --no-install-recommends gpg dirmngr gpg-agent \
  && rm -rf /var/lib/apt/lists/*

ENV TOMEE_VER=11.0.0-M2
ENV TOMEE_BUILD=plus
# SHA512 source: https://downloads.apache.org/tomee/tomee-11.0.0-M2/apache-tomee-11.0.0-M2-plus.tar.gz.sha512
ENV TOMEE_SHA512=643e7dcfe981573f5d11920296ff5b35e18c321a66128a357e7531f8b8a8908cb2fdd5dacbe8a2877f59cbf82086be0aab464d0a3acb993c4a2f7bf5bca7d85e
# Markus Jung (CODE SIGNING KEY), verified against Apache TomEE KEYS.
ENV TOMEE_GPG_KEY=85FBBE98D6C37CDA8A7D8FF9F9FF83A48D339D37

RUN set -eux; \
    ddist() { \
        local f="$1"; shift; \
        local distFile="$1"; shift; \
        local success=; \
        local distUrl=; \
        for distUrl in \
            https://downloads.apache.org/ \
            https://archive.apache.org/dist/ \
        ; do \
            if curl -fSL --retry 3 --connect-timeout 30 "$distUrl$distFile" -o "$f" && [ -s "$f" ]; then \
                success=1; \
                break; \
            fi; \
        done; \
        [ -n "$success" ]; \
    }; \
    archive="apache-tomee-${TOMEE_VER}-${TOMEE_BUILD}.tar.gz"; \
    ddist "$archive" "tomee/tomee-${TOMEE_VER}/$archive"; \
    ddist "$archive.asc" "tomee/tomee-${TOMEE_VER}/$archive.asc"; \
    ddist tomee.KEYS tomee/KEYS; \
    echo "$TOMEE_SHA512  $archive" | sha512sum -c -; \
    export GNUPGHOME="$(mktemp -d)"; \
    gpg --batch --import tomee.KEYS; \
    gpg --batch --export "$TOMEE_GPG_KEY" > tomee.gpg; \
    test -s tomee.gpg; \
    gpg --batch --no-default-keyring --keyring "$(pwd)/tomee.gpg" --verify "$archive.asc" "$archive"; \
    tar -zxf "$archive"; \
    mv "apache-tomee-${TOMEE_BUILD}-${TOMEE_VER}"/* /usr/local/tomee/; \
    rm -rf "apache-tomee-${TOMEE_BUILD}-${TOMEE_VER}" "$GNUPGHOME"; \
    rm "$archive" "$archive.asc" tomee.KEYS tomee.gpg; \
    rm bin/*.bat; \
    rm bin/*.exe; \
    rm bin/*.tar.gz*

EXPOSE 8080
CMD ["catalina.sh", "run"]
