# KishouScrapeDraw

**KishouScrapeDraw** は、気象庁（JMA）の天気データを取得・可視化し、PDF形式のレポートにまとめることができる教育向けPythonパッケージです。

生徒ごとのPDFをCSVファイルから一括生成することもでき、理科や地理の授業、探究学習などで活用できます。

---

## 主な機能

- 気象庁（JMA）サイトから天気データを自動取得
- 気温・降水量などのグラフ描画（日本語フォント対応）
- 天気図のダウンロードと自動トリミング
- PDFレポートの自動生成（グラフ・表・天気図を1枚にまとめる）
- 生徒名簿CSVを用いた一括PDF出力（クラス対応）

---

## システム前提条件（Linux / Google Colab など）

`KishouScrapeDraw` を正しく動作させるには、以下のシステムパッケージのインストールが必要です：

### 必須システムパッケージ

- `poppler-utils`（PDFから画像変換）
- `ghostscript`（PDF処理）
- `fonts-ipafont`（日本語フォント）

### Ubuntu / Debian の場合（例：Google Colab）

```bash
sudo apt-get update
sudo apt-get install -y poppler-utils ghostscript fonts-ipafont

### macOS の場合（Homebrew）
brew install poppler ghostscript
brew install --cask homebrew/cask-fonts/font-ipaexfont

### Windows の場合
Poppler for Windows をインストール
Ghostscript をインストール
IPAフォントを 公式サイト からインストール

## インストール

```bash
pip install KishouScrapeDraw
