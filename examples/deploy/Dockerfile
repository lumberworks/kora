# kora-cli on crates.io (v2.0.5) needs Rust >= 1.89 (Solana SDK deps)
FROM rust:1.89-bookworm

RUN cargo install kora-cli --version 2.0.5

WORKDIR /app
COPY kora.toml signers.toml ./

EXPOSE 8080

CMD kora --config /app/kora.toml --rpc-url ${RPC_URL} rpc start --signers-config /app/signers.toml --port ${PORT:-8080}
