FROM hugomods/hugo:exts-0.111.3

ARG USERNAME=vscode
# UID, GID are updated from VsCode to reflect local user.
ARG USER_UID=1001
ARG USER_GID=1001

RUN addgroup \
        --gid ${USER_GID} \
        ${USERNAME} \
    || echo "Already exists..."

RUN getent group ${USER_GID} | cut -d: -f1 > /tmp/group_name
RUN adduser \
        --disabled-password \
        --gecos "" \
        --shell /bin/ash \
        --ingroup $(cat /tmp/group_name) \
        --uid ${USER_UID} \
        ${USERNAME}

USER ${USERNAME}
