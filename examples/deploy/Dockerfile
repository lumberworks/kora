# kora-cli needs Rust >= 1.89 (Solana SDK deps). 2.2.0-beta.7+ fixes CPI burn inner-ix parsing.
FROM rust:1.89-bookworm

RUN cargo install kora-cli --version 2.2.0-beta.7

WORKDIR /app
COPY kora.toml signers.toml ./

EXPOSE 8080

CMD kora --config /app/kora.toml --rpc-url ${RPC_URL} rpc start --signers-config /app/signers.toml --port ${PORT:-8080}
