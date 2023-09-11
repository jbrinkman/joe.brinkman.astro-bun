FROM oven/bun:1.0 

ARG USERNAME=vscode
ARG USER_UID=1001
ARG USER_GID=${USER_UID}
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt update \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt install -y --no-install-recommends git sudo zsh curl \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

# set up oh my zsh
RUN cd ~ && sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
# initialize ZSH
# RUN /bin/zsh ~/.zshrc
# Switch back to root
USER root
