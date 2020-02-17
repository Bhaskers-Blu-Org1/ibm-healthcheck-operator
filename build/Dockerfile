FROM registry.access.redhat.com/ubi8/ubi-minimal:8.1-328

ENV OPERATOR=/usr/local/bin/health-service-operator \
    USER_UID=1001 \
    USER_NAME=health-service-operator

# install operator binary
COPY build/_output/bin/health-service-operator ${OPERATOR}

COPY build/bin /usr/local/bin
COPY manifests /manifests
RUN  /usr/local/bin/user_setup

ENTRYPOINT ["/usr/local/bin/entrypoint"]

USER ${USER_UID}