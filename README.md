# UltimateXIVMarkerManager (UXMM)

**FFXIVのフィールドマーカーを、床を見ながら整理・編集・保存するWindows用アプリ。**

**0.1.1.1（更新111回）** / Windows x64 / Dalamud不要

[English](README_EN.md) · [英語操作ガイド](docs/USER_GUIDE_EN.md) · [アプリをダウンロード](https://github.com/Lu-ci-el/UltimateXIVMarkerManager/releases/download/v0.1.1.1/UltimateXIVMarkerManager_0.1.1.1.zip) · [リリース内容](https://github.com/Lu-ci-el/UltimateXIVMarkerManager/releases/tag/v0.1.1.1) · [画像付き操作ガイド](docs/USER_GUIDE.md) · [旧版0.0.9.1のPDF説明書](docs/UltimateXIVMarkerManager_Manual_0.0.9.1.pdf)

![マーカープリセットとリアル戦闘MAPの説明用画面](docs/images/02-overview.png)

画面は9.1のUIに架空の配置とパスを表示した説明用サンプルです。床画像と図面の記号も説明用に作成しています。

## 最新版の変更

- Strategy Boardを新規作成し、素材の追加・削除・複製・種類変更、文章・色・透明度・反転・重なり順、図面名・背景を編集できます。
- 保存リスト・共有リストの両方を直接編集できます。共有図面を保存リストへ移動する必要はありません。両リスト間の移動・コピーにも対応しています。
- Ctrl＋クリックによる複数選択、まとめて移動、縦横整列、グリッド／近くのオブジェクトへの吸着、元に戻す／やり直すに対応しています。
- 編集開始後やウィンドウサイズ変更後に図面が縮み続ける不具合を修正しています。

操作は **Strategy Board → 保存リスト／共有リスト →「新規図面」または図面を選んで「編集」**。最大50オブジェクト、文章31バイト・図面名63バイト以内（UTF-8）です。FFXIVを終了してから「変更を保存」→確認画面の「DATへ保存」で反映します。

## リアル戦闘MAPの不具合・資料提供

**床が欠ける・違う床になる・模様がおかしい場合は、コンテンツ名と画面・再現条件をお寄せください。**

- [Issues：不具合報告・ログ・再現データの提供（日英フォーム）](https://github.com/Lu-ci-el/UltimateXIVMarkerManager/issues/new/choose)
- [Discussions：利用者同士の交流・質問・配置や資料の共有](https://github.com/Lu-ci-el/UltimateXIVMarkerManager/discussions/categories/general)
- [ファイル添付と報告内容の案内](.github/SUPPORT.md#日本語)

画像やZIPを添付できます。**調査・修正の可否は支援金の状況と開発時間によります。報告・資料提供・支援は修正や対応期限を保証しません。** 報告に支援は必須ではありません。

開発支援：**[Ko-fi](https://ko-fi.com/lost2)** / **[OFUSE](https://ofuse.me/lost)**

## 使い始める

1. リリースのアプリZIPをダウンロードし、フォルダごと展開します。
2. `UltimateXIVMarkerManager.exe`を起動します。必要な場合は[.NET 10 Desktop Runtime x64](https://dotnet.microsoft.com/en-us/download/dotnet/10.0)と[WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/)を導入します。
3. 有効な保存済みEXEを優先し、未設定なら標準のインストール場所を確認します。見つからない場合は「EXEを選択」でゲームの`game`フォルダにある`ffxiv_dx11.exe`を選びます。隣の`sqpack`からMAP名・画像・図面素材を取得し、保存構造を照合するために必須です。
4. 標準のドキュメント場所に一意のUISAVEがあれば自動選択します。複数キャラクターがある場合や見つからない場合は「UISAVEを選択」で対象キャラクターの`UISAVE.DAT`を開きます。場所の探し方は[操作ガイド](docs/USER_GUIDE.md#section-04)にあります。
5. マーカーを編集して「作業中Presetへ反映」。FFXIVを終了して「保存」を押し、保存枠と差分を確認します。

Library・独立マップへの保存と、ゲームのUISAVEへの保存は別の操作です。ゲームへの書き込み前にはバックアップと状態の確認を行います。

## 主な機能

| 機能 | 対応範囲 |
| --- | --- |
| マーカー編集 | ドラッグ・座標入力・枠入替・比較/Merge・Focus編集・選択枠の保存 |
| バックアップ / 復元 | 自動バックアップ、保存履歴からマーカー枠の復元 |
| Library | 配置の保管、フォルダ・タグ・メモ・お気に入り、Pack取込 |
| リアル戦闘MAP | 初期 / 設置場所・保存高さの切替、別高さのグレー表示、表示の移動、10%刻みのホイール倍率 |
| MAPキャッシュ | アプリ直下の`MAP`に永続保存、条件が一致する画像を再利用 |
| ゲームのStrategy Board | 保存/共有リストでの新規作成・直接編集、フォルダ開閉、外部保存・読込、挿入・削除、両リスト間の移動・コピー |
| 独立マップ / UXMM独自図面 | マップ単体保存、図面オブジェクトの編集、Map PACK作成・読込 |
| 既存共有コード | 既存オブジェクトの位置・表示等の限定編集。独自図面からのゲーム用コード新規生成は未対応 |

ゲームの保存/共有リスト内の図面は、UXMMの「Strategy Board」で編集・保存できます。「マップ」側のUXMM独自図面とは保存先が異なります。

全コンテンツの床選択・欠け・模様の一致は引き続き確認が必要です。ゲームの照明・発光・動くギミックや、リアルタイムのフェーズ判定は再現しません。

既知のMAP制限として、アロアロ島の設置場所／高さ選択時の外周切れ、天獄4層・再生4層・辺獄4層の前後半の表示分離が未解決です。0.1.1.1にはこれらのMAP修正を含みません。

## 説明書と外部ファイル

- [English illustrated guide](docs/USER_GUIDE_EN.md)：英語で起動・編集・保存・MAP・Strategyを説明。
- [画像付き操作ガイド](docs/USER_GUIDE.md)：起動準備、UISAVEの探し方、編集・保存、復元、MAP、Library、Strategyを説明。
- [旧版0.0.9.1のPDF説明書](docs/UltimateXIVMarkerManager_Manual_0.0.9.1.pdf)：ダウンロードして読みやすい版。
- [旧版0.0.9.1の説明書一式ZIP](https://github.com/Lu-ci-el/UltimateXIVMarkerManager/releases/download/v0.0.9.1/UltimateXIVMarkerManager_Manual_0.0.9.1.zip)：HTML・Markdown・PDF・画像をまとめたオフライン版。展開後に`USER_GUIDE.html`を開きます。

| 拡張子 | 用途 |
| --- | --- |
| `.mmp` | Map PACK |
| `.mms` | Strategyの保存リスト・保存フォルダ |
| `.mmsh` | Strategyの共有リスト |

対応する従来の`.uxmm`読込も保持しています。ファイル名を変えるだけでは形式は変換されません。

## 配布について

アプリ本体はリリースに添付しています。このリポジトリに置いているのは説明資料と配布情報です。**アプリの開発ソースは非公開です。** GitHubの「Source code (zip / tar.gz)」に含まれるのは、この配布リポジトリの説明資料です。

アプリZIPは署名済みの配布構成です。EXEだけを取り出さず、同梱ファイルをそのまま展開して使ってください。日本語README.txtと英語README_EN.txtを同梱しています。

不具合を伝える際はアプリ版・コンテンツ名・初期/設置場所/高さ・操作・エラー文を確認してください。画面のEXE / UISAVEパス、キャラクター情報、最近のファイル一覧を隠し、UISAVEや使用中の個人設定フォルダを一般公開しないでください。
