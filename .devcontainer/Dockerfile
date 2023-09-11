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
# RUN groupadd -r chromium && useradd   -d  ${BUN_DIR} -M -r -g chromium -G audio,video chromium \
#     && mkdir -p /home/chromium/Downloads && chown -R chromium:chromium /home/chromium
# USER chromium
# WORKDIR $BUN_DIR

# RUN sudo apt update 
   # && export DEBIAN_FRONTEND=noninteractive \
   # && sudo apt -y install --no-install-recommends zsh curl git
# chsh -s $(which zsh)

# set up oh my zsh
# RUN cd ~ && sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
# initialize ZSH
# RUN /bin/zsh ~/.zshrc
# Switch back to root
# USER root
USER $USERNAME
