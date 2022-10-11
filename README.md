# Blog Template on GitHub Pages

Markdown だけ書いて簡単に個人サイトを作るためのテンプレート．

## GitHub Pages で簡単にWebサイトを作る

1. このレポジトリを Fork する．（図1. 「+ Create a new fork」を押下し，Repository name や Description を設定し，「Create Fork」を押下して完了）  
または既存レポジトリの場合はこのレポジトリの中身を展開し直下に置く．
    * `/readme_figures` はこのファイルの画像なので消して良い．
2. `index.md` を編集する（トップページになる）．  
`/index.md` が存在しない場合は `/README.md` が代わりにトップページ `index.html` になる．  
    * ロゴ画像 `/assets/img/logo.png` やファビコン `/assets/favicons/` も差し替えれば反映される．
    [Favicon Generator. For real.](https://realfavicongenerator.net/) を使うと簡単にクロスプラットフォームのファビコンを設定できる．
3. 「Settings」タブ→「Pages」→ Branch を「master」に指定して Save（図2.）．
4. デプロイが終われば（「Actions」タブで進捗を確認できる．数分～十数分程度．）「Pages」の上部にWebサイトのリンクが表示される（図3.）．  
デフォルトのURLは `https://<ユーザー名(lower case)>.github.io/<レポジトリ名>/`．
5. レポジトリ内にさらに Markdown ファイルを作成すれば push するたび自動で ～～.html が生成され，公開される． 
`/posts/post1.md` を参照のこと．  
元の Markdown ファイルやその他のファイルもパスを指定すればアクセスできる．

![図1](readme_figures/fig1.png "図1")

![図2](readme_figures/fig2.png "図2")

![図3](readme_figures/fig3.png "図3")

## カスタマイズ

`_config.yml` で全体のパラメータを設定．

```yaml
title: Blog Template        # サイトの名前
description: Blog Template on GitHub Pages with Jekyll theme Miminal # サイトの説明
logo: /assets/img/logo.png  # ページ左上に表示されるロゴ画像
show_downloads: false       # ダウンロードボタンの表示
github:
  is_project_page: true     # プロジェクトページへのリンクの表示
  is_user_page: true        # ユーザーページへのリンクの表示
google_analytics:           # Google AnalyticsのトラッキングID
theme: jekyll-theme-minimal # テーマ
plugins:
  - jekyll-sitemap          # サイトマップを自動生成するプラグイン
configs:
  favicon_assets: /pages-blog-template-minimal/assets/favicons/ # ファビコンの所在
  is_multi_favicon: true    # マルチ県境サポートのファビコンを使用
  is_page_top: true         # ページトップに戻るボタンをフッターに表示
  is_update_date: true      # 最終更新日時をフッターに表示
```

* Markdown 冒頭の `---` で挟まれた領域にタイトルやレイアウトなど，ページパラメータを設定する．
* レイアウトのテンプレートを追加/変更する場合は `_layout/` を参照．
  * `{{ site.～～}}` で `_config.yml` のパラメータ，`{{ page.～～}}` でページのパラメータを参照できる．  
  `{% include ～～ %}` で  `_includes` 内のファイルを参照できる．  
  （Jekyllでビルドするタイミングで展開される）
* テーマを変更する場合は [使用できるテーマ](https://github.com/orgs/pages-themes/repositories) から選んで `_config.yml` の `theme` と `/assets/css/style.scss` の `@import ～～` を変更する．
* Google Analytics でトラッキングする際は `_config.yml` の `google_analytics` を設定する．
* Google Search Console の所有権確認を行う際は「HTMLタグ」を `_indludes/head-custom.html` 内に書くとよい．
