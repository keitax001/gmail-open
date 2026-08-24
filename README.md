# gmail-open

Discord 通知から iOS の Gmail アプリで該当メールを直接開くためのリダイレクトページ。

Discord（iOS）はメッセージ中の `googlegmail://` などのカスタムスキームをリンク化しないため、
いったんこの https ページを経由して `googlegmail:///cv=<メールID>/accountId=<番号>` へ転送する。

- 利用元: [gmail-watcher](https://github.com/keitax001) の Discord 通知（`notifier.py`）
- URL 形式: `https://<user>.github.io/gmail-open/#cv=<メールID>&acct=<アカウント番号>`
- メールIDは URL フラグメントでのみ受け渡すため、GitHub を含むどのサーバーにも送信されない。
