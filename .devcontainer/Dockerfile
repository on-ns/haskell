FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu-22.04

# 必要なパッケージと ghcup をインストール
RUN apt-get update && apt-get install -y curl xz-utils git build-essential libgmp-dev && \
    rm -rf /var/lib/apt/lists/* && \
    curl --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | BOOTSTRAP_HASKELL_NONINTERACTIVE=1 sh && \
    bash -lc "source ~/.ghcup/env && ghcup install ghc recommended --set && ghcup install cabal latest && ghcup install hls latest"

# PATH 設定
ENV PATH="/root/.ghcup/bin:${PATH}"
