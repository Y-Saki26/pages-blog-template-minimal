# Blog Template on GitHub Pages

Markdown だけ書いて簡単に個人サイトを作るためのテンプレート．

## GitHub Pages で簡単にWebサイトを作る

1. このレポジトリを Fork する．（図1. 「+ Create a new fork」を押下し，Repository name や Description を設定し，「Create Fork」を押下して完了）  
または既存レポジトリの場合はこのレポジトリの中身を展開し直下に置く．
    * `/readme_figures` はこのファイルの画像なので消して良い．
2. `index.md` でトップページとなる Markdown ファイルを指定する．  
`/index.md` が存在しない場合は `/README.md` が代わりにトップページ `index.html` になる．  
    * ロゴ画像 `/assets/img/logo.png` やファビコン `/assets/favicons/` も差し替えれば反映される．  
    [Favicon Generator. For real.](https://realfavicongenerator.net/) を使うと簡単にクロスプラットフォームのファビコンを設定できる．
3. 「Settings」タブ→「Pages」→ Branch を「master」に指定して Save（図2.）．
4. デプロイが終われば（「Actions」タブで進捗を確認できる．数分～十数分程度．）「Pages」の上部にWebサイトのリンクが表示される（図3.）．  
デフォルトのURLは `https://<ユーザー名(lower case)>.github.io/<レポジトリ名>/`．
5. レポジトリ内にさらに Markdown ファイルを作成すれば push するたび自動で ～～.html が生成され，公開される．  
`example.md` や  `/posts/post1.md` を参照のこと．  
元の Markdown ファイルやその他のファイルもパスを指定すればアクセスできる．

![図1](readme_figures/fig1.png "図1")  
:図1

![図2](readme_figures/fig2.png "図2")  
:図2

![図3](readme_figures/fig3.png "図3")  
:図3

## カスタマイズ

`_config.yml` で全体のパラメータを適宜設定．
不要なものは空欄でよい．

```yaml
title: Blog Template        # サイトの名前
lang: ja                    # 言語設定
url:                        # サイトのURL
tagline: short description  # サイトの説明(短)
description: long description # サイトの説明
author:                     # 著者情報
  name:                       # 著者名
  url:                        # 著者URL
twitter:                    # Twitter 設定
  username:                   # Twitter ユーザー名(あれば)
  card: summary               # Twitter にリンクを貼ったときの表示方法
logo: /assets/img/logo.png  # ページ左上に表示されるロゴ画像(レポジトリ直下から)
google_site_verification:   # Google Search Console の所有権の確認用タグのID
google_analytics:           # Google Analytics のトラッキングID
github:                     # GitHub 設定
  is_project_page: true       # プロジェクトページへのリンクの表示
  is_user_page: true          # ユーザーページへのリンクの表示
theme: jekyll-theme-minimal # テーマ
plugins:                    # Jekyll プラグイン
  - jekyll-sitemap            # サイトマップを自動生成するプラグイン
show_downloads: false       # ダウンロードボタンの表示
configs:                    # このテンプレート用の設定パラメータ
  favicon_assets: /pages-blog-template-minimal/assets/favicons/ # ファビコンの所在(ドメイン直下から)
  is_multi_favicon: true      # マルチ環境サポートのファビコンを使用
  is_mathjax: true            # MathJax(数式表示)を使用するかどうか
  is_pagetop_button: true     # ページトップに戻るボタンの表示
  is_homepage_button: true    # ホームページに戻るボタンの表示
```

* Markdown 冒頭の `---` で挟まれた領域に同様のYAML形式のタグを設定できる．
  * `title`，`layout`，`date`，`lastmod` などの設定を推奨．
* レイアウトのテンプレートを追加/変更する場合は `_layout/` を参照．
  * `{{ site.～～}}` でサイト全体のパラメータ(`_config.yml` で設定したもの)，`{{ page.～～}}` でページのパラメータを参照できる．  
  `{% include ～～ %}` で  `_includes` 内のファイルを参照できる．  
  （Jekyllでビルドするタイミングで展開される）
* テーマを変更する場合は [使用できるテーマ](https://github.com/orgs/pages-themes/repositories) から選んで `_config.yml` の `theme` を変更する．
* Google Analytics でトラッキングする際は `_config.yml` の `google_analytics` を設定する．
* Google Search Console の所有権確認を行う際は「HTMLタグ」を選択し，タグ内のIDを `_config.yml` の `google_site_verification` に設定する．
