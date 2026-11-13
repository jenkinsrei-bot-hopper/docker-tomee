FROM eclipse-temurin:17-jre-alpine

ENV PATH=/usr/local/tomee/bin:$PATH
RUN mkdir -p /usr/local/tomee ~/.gnupg

WORKDIR /usr/local/tomee

RUN apk add --no-cache gpg gpg-agent dirmngr curl\
  && rm -rf /var/cache/apk/*

ENV TOMEE_VER=11.0.0-M2
ENV TOMEE_BUILD=plume
# SHA512 source: https://downloads.apache.org/tomee/tomee-11.0.0-M2/apache-tomee-11.0.0-M2-plume.tar.gz.sha512
ENV TOMEE_SHA512=13ecdcdc02a2de4b483ad13d140739fc13b429086dae3f266c2b375ea0e6d1de17650caf42118a644ffac83bb01e60d70537b6930bf66878fad86f97d66e4d4c
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
