FROM eclipse-temurin:21.0.1_12-jre-jammy as mainstage
USER root
RUN id -u bist 1>/dev/null 2>&1 || (( getent group 0 1>/dev/null 2>&1 || ( type groupadd 1>/dev/null 2>&1 && groupadd -g 0 root || addgroup -g 0 -S root )) && ( type useradd 1>/dev/null 2>&1 && useradd --system --create-home --uid 1001 --gid 0 bist || adduser -S -u 1001 -G root bist ))
WORKDIR /opt/cicdexample
COPY --chown=bist:root . /opt
LABEL org.opencontainers.image.base.name="eclipse-temurin:21.0.1_12-jre-jammy"
LABEL org.opencontainers.image.vendor="bist"
USER 1001:0
ENTRYPOINT ["/opt/cicdexample/bin/cicdexample"]
CMD []