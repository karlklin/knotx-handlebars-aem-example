FROM knotx/knotx:$knotx_version

LABEL maintainer="Knot.x Project"

COPY ./out/knotx /usr/local/knotx

HEALTHCHECK --interval=5s --timeout=2s --retries=12 \
  CMD curl --silent --fail localhost:8092/healthcheck || exit 1

RUN sed -i 's/# JVM_DEBUG=/JVM_DEBUG=/g' /usr/local/knotx/bin/knotx

CMD [ "knotx", "run-knotx" ]