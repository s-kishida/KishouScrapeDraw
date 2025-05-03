# KishouScrapeDraw

**KishouScrapeDraw** は、気象庁（JMA）の天気データを取得・可視化し、PDF形式のレポートにまとめることができる教育向けPythonパッケージです。

生徒ごとのレポートをCSVファイルから一括生成する機能も備えており、理科や地理の授業、探究学習などで活用できます。

---

## 🌟 主な機能

- 気象庁（JMA）サイトから天気データを自動取得
- 日本語フォント対応のグラフ描画（matplotlib + japanize_matplotlib）
- 天気図のダウンロードとトリミング（OpenCV使用）
- PDFレポートの生成（fpdfによる日本語対応）
- 生徒名簿CSVを用いた一括レポート出力（クラス単位での自動生成）

---

## 📦 インストール方法

```bash
pip install KishouScrapeDraw
```

※ Python 3.8 以上を推奨

---

## 🛠 システム前提条件（Linux / Google Colab など）

本パッケージを利用するには、以下の **システムパッケージ** のインストールが必要です：

### ✅ 必須パッケージ

- `poppler-utils`（PDF → 画像変換）
- `ghostscript`（PDF処理）
- `fonts-ipafont`（日本語フォント）

### Ubuntu / Google Colab の場合

```bash
sudo apt-get update
sudo apt-get install -y poppler-utils ghostscript fonts-ipafont
```

### macOS の場合（Homebrew）

```bash
brew install poppler ghostscript
brew install --cask homebrew/cask-fonts/font-ipaexfont
```

### Windows の場合

- [Poppler for Windows](http://blog.alivate.com.au/poppler-windows/)
- [Ghostscript](https://www.ghostscript.com/download/gsdnld.html)
- [IPAフォント公式サイト](https://ipafont.ipa.go.jp/) からフォントをインストール

---

## 🚀 使用例

```python
from kishouscrapedraw import scraper, grapher, pdf_generator

# データ取得
data = scraper.fetch_weather_data("Tokyo")

# グラフ描画
grapher.plot_temperature(data)

# PDF出力
pdf_generator.generate_report(data, output_path="report.pdf")
```

---

## 📂 生徒CSVファイルからの一括出力

```python
from kishouscrapedraw import batch_report

batch_report.generate_from_csv("students.csv")
```

CSVのフォーマット例：

```
name,location,date
山田太郎,Tokyo,2025-05-01
佐藤花子,Osaka,2025-05-01
```

---

## 📚 依存ライブラリ

以下のPythonライブラリが `pip install` 時に自動でインストールされます：

- `matplotlib`
- `japanize_matplotlib`
- `pandas`, `numpy`
- `fpdf`, `PyPDF2`, `pdf2image`
- `requests`
- `qrcode[pil]`
- `opencv-python-headless`

---

## 🧑‍🏫 開発者

- **S.Kishida**（<s.kishida98@gmail.com>）
- 青翔開智｜教育実践プロジェクト

---

## 📄 ライセンス

このパッケージは **MITライセンス** のもとで公開されています。

---

## 🔗 GitHubリポジトリ

https://github.com/s-kishida/KishouScrapeDraw.git
