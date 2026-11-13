FROM ibm-semeru-runtimes:open-25-jre-jammy

ENV PATH=/usr/local/tomee/bin:$PATH
RUN mkdir -p /usr/local/tomee ~/.gnupg

WORKDIR /usr/local/tomee

RUN apt-get update \
  && apt-get install -y --no-install-recommends gpg dirmngr gpg-agent \
  && rm -rf /var/lib/apt/lists/*

ENV TOMEE_VER=10.3.0
ENV TOMEE_BUILD=webprofile
# SHA512 source: https://downloads.apache.org/tomee/tomee-10.3.0/apache-tomee-10.3.0-webprofile.tar.gz.sha512
ENV TOMEE_SHA512=6c0ca666939535e3d4fb091e9155e85fd2dfe6f4f84035f84cb156574ce48c7a920d3f58ba3c1485a9a81b4735b96a1491f36776f17ab2a0084e3b8eb979b167
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
