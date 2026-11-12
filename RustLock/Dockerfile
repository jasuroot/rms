  # Build bosqichi
  FROM rust:1.85 AS builder

  WORKDIR /app

  COPY Cargo.toml Cargo.lock ./
  COPY src ./src

  RUN cargo build --release

  # Ishga tushirish bosqichi
  FROM debian:bookworm-slim

  WORKDIR /app

  COPY --from=builder /app/target/release/rustlock/usr/local/
  bin/app

  CMD ["app"]