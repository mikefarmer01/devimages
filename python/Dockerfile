FROM ghcr.io/mikefarmer01/devimage-base:latest
LABEL maintainer="Michael Bauer"

LABEL name="mikefarmer01/devimage-python"
LABEL version="ubi9"

#labels for container catalog
LABEL summary="Python devfile"
LABEL description="Devfile for Python developments. Includes Poetry and black"
LABEL io.k8s.display-name="devfile-developer-python"
LABEL io.openshift.expose-services=""

USER 0

# Python
RUN dnf -y install python3-devel python3-setuptools python3-pip nss_wrapper

RUN pip install pipx
RUN pipx install poetry && \
    pipx install pre-commit && \
    pipx install black

# cleanup dnf cache
RUN dnf -y clean all --enablerepo="*"

USER 10001

