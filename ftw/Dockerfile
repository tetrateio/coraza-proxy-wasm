# Copyright 2022 The OWASP Coraza contributors
# SPDX-License-Identifier: Apache-2.0

FROM ghcr.io/coreruleset/go-ftw:0.6.4

RUN apk update && apk add curl

WORKDIR /workspace

# TODO update when new CRS version is tagged: https://github.com/coreruleset/coreruleset/archive/refs/tags/v4.0.0-rc2.tar.gz
ADD https://github.com/coreruleset/coreruleset/tarball/1d95422bb31983a5290720b7fb662ce3dd51f753 /workspace/coreruleset/
RUN cd coreruleset && tar -xf 1d95422bb31983a5290720b7fb662ce3dd51f753 --strip-components 1

COPY ftw.yml /workspace/ftw.yml
COPY tests.sh /workspace/tests.sh

ENTRYPOINT ["sh"]
CMD ["-c", "/workspace/tests.sh"]

