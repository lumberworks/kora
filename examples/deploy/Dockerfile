# kora-cli from git: crates.io 2.2.0-beta.7 lacks CPI parsed-type support for
# initializeTransferHook / updateTransferHook (Token-2022 transfer hooks).
FROM rust:1.91.1-bookworm

ARG KORA_GIT_REV=main
RUN cargo install --git https://github.com/lumberworks/kora.git --rev ${KORA_GIT_REV} --locked kora-cli

WORKDIR /app
COPY kora.toml signers.toml ./

EXPOSE 8080

CMD kora --config /app/kora.toml --rpc-url ${RPC_URL} rpc start --signers-config /app/signers.toml --port ${PORT:-8080}
