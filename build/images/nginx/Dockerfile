FROM k8s.gcr.io/debian-base:v2.0.0

ENV TERRAFORM_VERSION 0.12.19

RUN clean-install \
    bash \
    curl \
    ca-certificates \
    unzip \
    git \
    openssh-client

RUN curl -sSL -o /terraform.zip "https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip" \
    && unzip /terraform.zip -d /usr/bin \
    && rm -rf /terraform.zip

COPY entrypoint.sh /

CMD [ "/entrypoint.sh" ]
