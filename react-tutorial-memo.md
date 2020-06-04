# reactチュートリアルメモ

[チュートリアル：React の導入 – React](https://ja.reactjs.org/tutorial/tutorial.html)

> ここにある指示に従って、エディタ上でシンタックスハイライティングを設定することをお勧めします。

> もし問題にはまったら、コミュニティーによるサポート情報をチェック

> Reactiflux Chat は迅速なヘルプが得られます

> () => を書くのを忘れて onClick={alert('click')} と書くのはよくある間違いであり、こうするとコンポーネントが再レンダーされるたびにアラートが表示されてしまいます

> 開発者向けツールを CodePen で動作させるには追加のステップが必要

> React 用語でいうと、Square コンポーネントは制御されたコンポーネント (controlled component) になった

> 関数コンポーネントとは、render メソッドだけを有して自分の state を持たないコンポーネントを、よりシンプルに書くための方法

- 続き
  - [「タイムトラベル機能の追加」から](https://ja.reactjs.org/tutorial/tutorial.html#adding-time-travel)

## React Hooksの調査

- [安全に React Hooks を使用する - Qiita](https://qiita.com/kobayang/items/88a104c0be28e16e65e8)
  - React Hook useEffect has a missing dependency: 'queryParams.debug'. Either include it or remove the dependency array  react-hooks/exhaustive-deps
- [フックの導入 – React](https://ja.reactjs.org/docs/hooks-intro.html)
  - [ ] この問題を解決するためのレンダープロップや高階コンポーネントといったパターン
  - [ ] この点については独自フックの作成にてより詳しく述べていきます。
  - [ ] より state 管理を予測しやすくするため、必要に応じてリデューサ (reducer) を使って管理するようにしてもよい
  - [ ] 副作用フックの利用法
  - [ ] Hook の FAQ ページ
- [フック早わかり – React](https://ja.reactjs.org/docs/hooks-overview.html)
  - [ ] useState と this.state の違いについてはステートフックの利用で例を挙げて説明
  - [ ] 配列の分割代入構文を使うことで、useState を呼び出して宣言した state 変数に、異なる名前をつけることができます
  - [ ] これらのメソッドと useEffect との違いについては副作用フックの利用法で例を挙げて説明します
  - [ ] これらのルールを自動的に強制するための linter plugin を用意
  - [ ] useContext
  - [ ] useReducer
- [ステートフックの利用法](https://ja.reactjs.org/docs/hooks-state.html)
  - [ ] 独立した state 変数を分割する際の推奨事項については FAQ で詳しく述べています。
  - [ ] あとでカスタマイズする方法について説明
  - 「レンダーの後」に副作用は起こる
- [副作用フックの利用法 – React](https://ja.reactjs.org/docs/hooks-effect.html)
  - [ ] これがなぜバグの回避につながるのか、そしてこれがパフォーマンスの問題を引き起こしている場合にどうのようにしてこの挙動を止めるのかについて説明します。
  - [ ] [副作用を使う場合のヒント](https://ja.reactjs.org/docs/hooks-effect.html#tips-for-using-effects)
- [フックのルール – React](https://ja.reactjs.org/docs/hooks-rules.html)
- [独自フックの作成 – React](https://ja.reactjs.org/docs/hooks-custom.html)
- [フック API リファレンス – React](https://ja.reactjs.org/docs/hooks-reference.html)
  - [ ] [フックに関するよくある質問 – React](https://ja.reactjs.org/docs/hooks-faq.html)
  - state の遅延初期化
  - state 更新の回避
  - useEffect に渡された関数はレンダーの結果が画面に反映された後に動作
  - 例えばユーザに見えるような DOM の改変は、ユーザが見た目の不整合性を感じずに済むよう、次回の描画が発生する前に同期的に発生する必要があります
    - [useLayoutEffect](https://ja.reactjs.org/docs/hooks-reference.html#uselayouteffect)
    - 参考 : [useEffect vs useLayoutEffect意訳 | 武骨日記](https://kenjimorita.jp/useeffect-vs-uselayouteffect-japanese/)
  - 条件付きで副作用を実行する
    - もしも副作用とそのクリーンアップを 1 度だけ（マウント時とアンマウント時にのみ）実行したいという場合、空の配列 ([]) を第 2 引数として渡すことができます
    - [ ] 通常はこちらやこちらのように、副作用を過度に再実行しないためのよりよい解決方法があります

useContextから

