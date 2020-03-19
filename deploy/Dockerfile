FROM docker:19.03.2

LABEL version="1.0.0"
LABEL repository="http://github.com/redhat-cop/github-actions"
LABEL homepage="http://github.com/redhat-cop/github-actions/deploy"
LABEL maintainer="Red Hat CoP"
LABEL "com.github.actions.name"="deploy helm"
LABEL "com.github.actions.description"="Runs helm template"
LABEL "com.github.actions.icon"="package"
LABEL "com.github.actions.color"="purple"

RUN apk --no-cache add bash curl tar && \
    cd /tmp && \
    curl -L https://get.helm.sh/helm-v3.1.2-linux-amd64.tar.gz | tar xvz && \
    cp /tmp/helm /usr/bin/ 

RUN apk --no-cache add bash curl tar && \
    cd /tmp && \
    curl -L0 https://storage.googleapis.com/kubernetes-release/release/v1.17.0/bin/linux/amd64/kubectl | tar xvz && \
    chmod +x /tmp/kubectl && \
    cp /tmp/kubectl /usr/bin/ && \

ADD entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
