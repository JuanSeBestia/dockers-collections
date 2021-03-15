FROM argoproj/argocd:v1.8.4

USER root
RUN apt-get update && \
    apt-get install -y \
        curl && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

USER argocd

ARG HGIT_PLUGIN_VERSION="0.10.0"
ARG HGIT_PLUGIN_REPO="https://github.com/aslafy-z/helm-git "

RUN helm plugin install ${HGIT_PLUGIN_REPO} --version ${HGIT_PLUGIN_VERSION}

ENV HELM_PLUGINS="/home/argocd/.local/share/helm/plugins/"