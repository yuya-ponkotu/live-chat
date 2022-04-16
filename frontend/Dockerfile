
# nodeのstable版を公式ページから確認し、DockerHubからalpineベースのものを指定
FROM node:16.2.0

# docker-compose.ymlからWORKDIRの値を受け取る
ARG WORKDIR

# コンテナのホームディレクトリを設定する
ENV HOME=/${WORKDIR}

# コマンド実行する作業ディレクトリの設定する
WORKDIR ${HOME}

# Alpineのリポジトリから最新インデックスを取得し、npm自体も最新版に更新する
RUN apt update && npm install -g npm && npm install --global @vue/cli@latest && npm install --save axios

# Viteで開発サーバーを起動する
CMD ["npm", "run", "serve"]