# kora-cli from git: crates.io 2.2.0-beta.7 lacks CPI parsed-type support for
# initializeTransferHook / updateTransferHook (Token-2022 transfer hooks).
FROM rust:1.91.1-bookworm

# Use --branch for branch names (libgit2 can fail to resolve --rev main).
# You can still pin a SHA by setting KORA_GIT_REF to the commit hash.
ARG KORA_GIT_REF=main
RUN cargo install --git https://github.com/lumberworks/kora.git --branch ${KORA_GIT_REF} --locked kora-cli

WORKDIR /app
COPY kora.toml signers.toml ./

EXPOSE 8080

CMD kora --config /app/kora.toml --rpc-url ${RPC_URL} rpc start --signers-config /app/signers.toml --port ${PORT:-8080}
