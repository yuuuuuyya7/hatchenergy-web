# hatchenergy-web

合同会社HatchEnergy コーポレートサイト（GitHub Pages で公開）

公開URL: https://hatchenergy.co.jp/

## 構成

| ファイル | 役割 |
|---|---|
| `index.html` | トップページ（1ページ完結LP）。CSS/JS はインライン |
| `privacy.html` | プライバシーポリシー |
| `CNAME` | 独自ドメイン設定（`hatchenergy.co.jp`）。**消さないこと** |
| `.nojekyll` | Jekyll のビルドを無効化（`_` 始まりのファイルが無視されるのを防ぐ） |
| `robots.txt` / `sitemap.xml` | クローラ向け |

外部依存は Google Fonts のみ。ビルド不要で、ファイルを置けばそのまま動きます。

## 更新のしかた

1. `index.html` を編集
2. コミットして `main` に push
3. 1〜2分で https://hatchenergy.co.jp/ に反映（反映されない場合はスーパーリロード）

```bash
git add -A
git commit -m "更新内容"
git push
```

## お問い合わせフォームについて

現在は **メーラー起動モード** です。送信ボタンを押すと、入力内容を差し込んだ状態で
メールソフトが起動します（送信先 `info@hatchenergy.co.jp`）。

Slack通知（GAS経由）に切り替えるときは、`index.html` の下部にあるこの1行を
GASウェブアプリの `/exec` URL に差し替えるだけです。

```js
var FORM_ENDPOINT = "https://script.google.com/macros/s/XXXXXXXXXXXXXXXXXXXXXXXX/exec";
```

差し替えると自動的にPOST送信モードに切り替わり、ボタン文言も戻ります。
詳細は Obsidian の `04_問い合わせフォーム設定.md` を参照。

## 注意

- Slack Webhook URL などの秘密情報は **このリポジトリに置かない**（`.gitignore` 済み）
- FAQ を変更したら `index.html` 内の JSON-LD（`FAQPage`）も同時に更新すること
- 会社情報を変更したら JSON-LD（`Organization`）と `privacy.html` も同時に更新すること
