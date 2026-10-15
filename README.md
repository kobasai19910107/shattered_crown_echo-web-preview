# shattered_crown_echo — Web UI preview

iPhone Safari 横持ち専用の開発版テストサイト。**本番の `shattered_crown_echo` とは別リポジトリです。**

- テスト版URL（GitHub Pages設定完了後）：https://kobasai19910107.github.io/shattered_crown_echo-web-preview/
- 本番：https://kobasai19910107.github.io/shattered_crown_echo/
- 元ソース：https://github.com/kobasai19910107/shattered_crown_echo/tree/feature/web-ui-v0-6
- ビルド：Godot 4.7.2、Windows版/EOSは変更しない
- ワークフロー：`.github/workflows/deploy-preview.yml`

## Pagesの初期設定（本リポジトリで1回だけ）
1. このリポジトリの **Settings → Pages** を開く。
2. **Build and deployment → Source** を **GitHub Actions** にする。
3. 右上の **Actions** で **Build and publish iPhone Web preview → Run workflow** を実行する（または初回実行を再実行）。
4. 正常終了後、上記テスト版URLをiPhone Safariで開く。

開発元のfeatureブランチを自動追跡して公開するのは**このプレビュー側のworkflowを起動した時だけ**です。元ソースのpushが本番Pagesにデプロイされることはありません。

## 本番セーブデータの保護
2つの `github.io` プロジェクトサイトは同一ホスト名なので、URLのパスが違うだけではブラウザの同一オリジン保存領域を完全に分離できません。プレビュービルドではビルド時に `config/name` とGodot `user://` の保存ファイル名を専用の名前空間へ切り替えます。変換はCI内だけで行い、元ソースは変更しません。

ブラウザのサイトデータ削除やキャッシュ消去は**本番セーブデータにも影響する可能性があるため行わない**でください。

## 実機テスト
縦画面の回転案内、iPhone横向きでのタイトル・拠点・戦闘・装備・鍛冶屋・商人・宝箱・イベント・戦利品確保。装備/宝箱/商人の候補は1回目で詳細、2回目で確定。Safariでの視認性、ノッチ、スワイプ、再起動後のセーブ復元を確認。
