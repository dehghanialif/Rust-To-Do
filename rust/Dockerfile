FROM ubuntu:oracular as builder

ARG USERNAME=rustdev
ARG USER_UID=1001
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt-get update \
    && apt-get install -y sudo curl git build-essential \
    && echo "$USERNAME ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME \
    && mkdir -p /workspace \
    && chown -R $USERNAME:$USERNAME /workspace

USER $USERNAME
WORKDIR /workspace

RUN curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | bash -s -- -y
ENV PATH="/home/${USERNAME}/.cargo/bin:${PATH}"

COPY --chown=${USERNAME}:${USERNAME} . .
RUN cargo build --release



FROM ubuntu:oracular

WORKDIR /app

COPY --from=builder /workspace/target/release/todo-backend .

EXPOSE 8080

CMD ["./todo-backend"]