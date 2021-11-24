FROM gitpod/workspace-full

# Ohmyzsh
RUN sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Install node version 16 and set it as default
RUN bash -c ". .nvm/nvm.sh && nvm install 16 && nvm use 16 && nvm alias default 16"

RUN npm install --global diff-so-fancy npm

# CA certs
RUN sh -c "sudo apt-get install --reinstall ca-certificates"

ENV CRD_VERSION="v1.0.10"
# crd2pulumi
RUN sh -c "curl -OL https://github.com/pulumi/crd2pulumi/releases/download/${CRD_VERSION}/crd2pulumi-${CRD_VERSION}-linux-amd64.tar.gz && \
  tar -xf crd2pulumi-${CRD_VERSION}-linux-amd64.tar.gz && \
  sudo mv crd2pulumi /usr/local/bin && \
  rm -f README.md LICENSE crd2pulumi-${CRD_VERSION}-linux-amd64.tar.gz"
