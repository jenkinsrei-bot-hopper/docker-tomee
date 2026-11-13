FROM eclipse-temurin:25-jre-noble

ENV PATH=/usr/local/tomee/bin:$PATH
RUN mkdir -p /usr/local/tomee ~/.gnupg

WORKDIR /usr/local/tomee

RUN apt-get update \
  && apt-get install -y --no-install-recommends gpg dirmngr gpg-agent curl \
  && rm -rf /var/lib/apt/lists/*

ENV TOMEE_VER=10.3.0
ENV TOMEE_BUILD=plume
# SHA512 source: https://downloads.apache.org/tomee/tomee-10.3.0/apache-tomee-10.3.0-plume.tar.gz.sha512
ENV TOMEE_SHA512=17c05305ad888b3f5fa2cab1dd126463a403ccfcaf475efe81438c587d4982582f010923bfa984bc9c6d62e951afcee5a8be18059a69cea10b02712253742d09
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
