# 予想収益シミュレーション (Projected Revenue Simulator)

このプロジェクトは広告宣伝費に応じた売上・利益の推移を探索・可視化するためのサンプルアプリです。
主に以下のファイルを含みます。

- `app.py`: Streamlit を使った Web UI（メインアプリ）
- `app.ipynb`: 同じ解析を Notebook 形式で実験できるファイル
- `.venv/`: 開発用の仮想環境（.gitignore に含める）
- `requirements.txt`: 現在の仮想環境にインストールされているライブラリ一覧

## 前提（推奨）
- macOS または類似 Unix 環境
- Python 3.13 系（プロジェクトの仮想環境は Python 3.13 を使用しています）
- 仮想環境（venv）を必ず使用してください。Homebrew 管理 Python やシステム Python に直接 pip インストールするのは避けてください。

## セットアップ手順
1. リポジトリをクローン（またはこのディレクトリに移動）:
```zsh
cd "/Users/kousei/Desktop/python実践(4)"
```
2. 仮想環境を作成して有効化（初回のみ）:
```zsh
python3 -m venv .venv
source .venv/bin/activate
```
3. 依存ライブラリのインストール:
```zsh
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

## アプリの起動
- Streamlit アプリの実行:
```zsh
source .venv/bin/activate
python -m streamlit run app.py --server.port=8501
```
ブラウザで `http://localhost:8501` を開くとアプリが表示されます。

- JupyterLab を使う場合:
```zsh
source .venv/bin/activate
python -m jupyter lab
```
ノートブックで `app.ipynb` を開き、カーネルとしてワークスペースの Python (`.venv/bin/python`) を選択してください。

## カーネルの登録（必要に応じて）
ワークスペースのカーネルを Jupyter に登録して VS Code や Jupyter から選べるようにします。
```zsh
python -m ipykernel install --user --name python_practical4 --display-name "Python (python実践(4))"
```

## よくある問題と対処
- pip の `externally-managed-environment` エラー: Homebrew 管理の Python の場合に表示されます。仮想環境を使用してインストールするか、pipx を検討してください。
- Streamlit の警告 `missing ScriptRunContext`: スクリプトを `python app.py` で実行すると出ます。必ず `streamlit run app.py` で起動してください。
- `ipykernel` インストールで失敗する・遅い場合:
  - まず仮想環境を有効にし、`pip install --upgrade pip setuptools wheel` を実行してから `pip install --prefer-binary ipykernel` をお試しください。
  - それでも遅い場合は `conda`（Miniforge）を使ってバイナリでインストールするのを推奨します。
- データが正しく描画されない場合: Jupyter ノートブックで `data_ad_cost`, `data_earnings`, `data_profit` のセルを上から順に実行して、DataFrame の整合性を確認してください。

## 開発・コミット・プッシュの基本
- ワークスペースの仮想環境やログをコミットしないよう `.gitignore` に設定済みです。必要なら `.gitignore` を更新してください。
- 変更を push する手順:
```zsh
git add -A
git commit -m "説明的なメッセージ"
git push origin main
```

## 補足
- ノートブック `app.ipynb` は差分が大きくなりやすいので、チーム運用を考える場合は Notebook の扱いを検討してください（たとえば .ipynb を除外し、スクリプトやテストに置き換えるなど）。

README を更新、要望や追加したい点があれば教えてください。
# Projected-Revenue-Simulator
