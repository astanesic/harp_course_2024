# Pre-built Dev Container Image for R. More info: https://github.com/rocker-org/devcontainer-images/pkgs/container/devcontainer%2Ftidyverse
# Available R version: 4, 4.1, 4.0
ARG VARIANT="4.2"
FROM ghcr.io/rocker-org/devcontainer/tidyverse:${VARIANT}

RUN apt-get update && apt-get install -y libproj-dev

RUN install2.r --error --skipinstalled -n -1 \
        statip \
        patchwork \
        here \
        remotes\
    && rm -rf /tmp/downloaded_packages \
    && R -q -e 'remotes::install_github("harphub/harp")'
