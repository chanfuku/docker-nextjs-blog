### [nextjsチュートリアルはこちら](https://nextjs.org/learn/basics/create-nextjs-app)

### docker環境
```
# 初回は5分ほどかかります
$docker-compose up -d
```
[localhost:3000](localhost:3000)が表示されればOK

## 学習メモ
- next.jsはデフォルトでページ描画がpre-renderingになるので、javascript無効にしても表示できるが、pure React.jsにはpre-renderingはないので表示できない。
- Static Generation vs Server-side Renderingだと、Static Generationが推奨されている。CDNで配信するならその方が早いという理由。なので、まずStatic Generationの採用を選択し、要件次第でServer side Renderingを選択する。頻繁に変わるページはStatic Generationには向いていない。最新のデータを表示する様なページはServerSideRendering.
- ImageコンポーネントがデフォルトでNext.jsに含まれている。Nuxtだとプラグインを追加する必要があるのでありがたい。
- CSSModulesを使うとcssのスコープをコンポーネントレベルに抑えることができる。
- globalなcssはpages/app.js以外では定義できない。
- getStaticsPropsでページに出力するデータを取得する。pagesファイル以外では使えない。server-sideで実行される。
- ユーザのダッシュボード等のページ内容は頻繁に変わるのでpre-renderingではなく、fetch data on the client-side。
- client-sideでデータ取得が必要な場合はReact hook (SWR)の仕様を推奨。
- markdwonをhtmlに変換してくれるremarkというライブラリ。
- githubがtokenを指定しないとpushできないようになっていた。つい1週間前位まではいけたのに。
- vueはページのHTMLをtemplate内に書いていたが、Reactではjavascriptの関数の中に記述するので、vueのtemplate構文よりも柔軟性があり、templateがカオスになりがち問題を回避できそうな気がする。
