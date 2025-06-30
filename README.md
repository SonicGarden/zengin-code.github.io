# Zengin Code API

[![GitHub Pages](https://github.com/zengin-code/zengin-code.github.io/workflows/GitHub%20Pages/badge.svg)](https://github.com/zengin-code/zengin-code.github.io/actions)

統一金融機関コードのJSON APIを提供するサイトです。

## API エンドポイント

- **全金融機関一覧**: https://zengin-code.github.io/api/banks.json
- **特定金融機関の支店一覧**: https://zengin-code.github.io/api/branches/{金融機関コード}.json

## 使用例

```bash
# 全金融機関一覧
curl https://zengin-code.github.io/api/banks.json

# みずほ銀行（0001）の支店一覧
curl https://zengin-code.github.io/api/branches/0001.json
```

## データ形式

### banks.json
```json
{
  "0001": {
    "code": "0001",
    "name": "みずほ",
    "kana": "ミズホ",
    "hira": "みずほ",
    "roma": "mizuho"
  }
}
```

### branches/{code}.json
```json
{
  "001": {
    "code": "001",
    "name": "東京営業部",
    "kana": "トウキョウエイギョウブ",
    "hira": "とうきょうえいぎょうぶ",
    "roma": "tokyoeigyobu"
  }
}
```

## プログラミング言語別ライブラリ

- [Ruby](https://github.com/zengin-code/zengin-rb) - `gem install zengin_code`
- [JavaScript/Node.js](https://github.com/zengin-code/zengin-js) - `npm install zengin-code`
- [Python](https://github.com/zengin-code/zengin-py) - `pip install zengin_code`

## 開発

このサイトは GitHub Pages で自動的にホスティングされています。

### ディレクトリ構造

```
source-data/          # 元データ（サブモジュール）
├── data/
│   ├── banks.json   # 金融機関マスタ
│   └── branches/    # 支店データ
│       ├── 0001.json
│       ├── 0005.json
│       └── ...
index.html           # API ドキュメント
.github/workflows/   # GitHub Actions設定
└── pages.yml        # 自動デプロイ設定
```

### デプロイ

以下のタイミングで自動的にデプロイされます：

- `master` ブランチへのプッシュ
- 毎日 4:30 JST（定期実行）
- 手動実行

## ライセンス

MIT License
