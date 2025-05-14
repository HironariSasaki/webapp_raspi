FROM python:3.12-slim

# 作業ディレクトリを設定
WORKDIR /app

# 必要な依存関係をインストール
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# アプリケーションコードをコピー
COPY . .

# アプリケーションを実行
CMD ["python", "app.py"]
