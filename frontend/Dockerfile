# Node.js 22.x系のイメージを使います
FROM node:22

# 作業ディレクトリを設定
WORKDIR /app

# 必要なファイルをコピー
COPY frontend/package*.json ./

# 依存パッケージをインストール
RUN npm install

# フロントエンドのソースコードをコピー
COPY frontend /app

# Vue.js のビルドを実行
RUN npm run build

# Nginxでフロントエンドを提供する準備
FROM nginx:alpine
COPY --from=0 /app/dist /usr/share/nginx/html

# Nginxを使ってポート80で提供
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
