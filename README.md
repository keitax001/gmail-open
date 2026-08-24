# gmail-open

Discord 通知から iOS の Gmail アプリで該当メールを直接開くためのリダイレクトページ。

Discord（iOS）はメッセージ中の `googlegmail://` などのカスタムスキームをリンク化しないため、
いったんこの https ページを経由して `googlegmail:///cv=<メールID>/accountId=<番号>` へ転送する。

- 利用元: [gmail-watcher](https://github.com/keitax001) の Discord 通知（`notifier.py`）
- URL 形式: `https://<user>.github.io/gmail-open/#cv=<メールID>&acct=<アカウント番号>`
- メールIDは URL フラグメントでのみ受け渡すため、GitHub を含むどのサーバーにも送信されない。

## 既知の制限（2026-08 実機検証）

現行の Gmail iOS アプリは `cv=` によるメッセージ指定を無視するため、開けるのは受信箱まで。
hex/10進ID・accountId 各種（番号/メールアドレス/省略）・`search?q=rfc822msgid:` 等の
8形式を実機で総当たりし、全て受信箱止まりだった。メッセージ単位の deep link は現状不可能。
`cv=` は仕様復活に備えて付けたままにしている。
