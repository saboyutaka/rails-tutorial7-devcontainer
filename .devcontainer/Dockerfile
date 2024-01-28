# [Choice] Ruby version (use -bullseye variants on local arm64/Apple Silicon): 3, 3.1, 3.0, 2, 2.7, 2.6, 3-bullseye, 3.1-bullseye, 3.0-bullseye, 2-bullseye, 2.7-bullseye, 2.6-bullseye, 3-buster, 3.1-buster, 3.0-buster, 2-buster, 2.7-buster, 2.6-buster
ARG VARIANT=3.1-bullseye
FROM mcr.microsoft.com/vscode/devcontainers/ruby:0-${VARIANT}

# [Choice] Node.js version: lts/*, 16, 14, 12, 10
ARG NODE_VERSION="16"
RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"

ARG BUNDLER_VERSION='2.3.14'
RUN gem install bundler -v ${BUNDLER_VERSION}
ENV BUNDLE_PATH='/usr/local/bundle'

# Install Rails
ARG RAILS_VERSIONS='7.0.3'
RUN gem install rails -v ${RAILS_VERSIONS}
RUN gem install ruby-lsp
