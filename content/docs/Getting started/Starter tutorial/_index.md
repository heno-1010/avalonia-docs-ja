---
weight: 4
---
# スターターチュートリアル

## 温度変換アプリの作成
Avaloniaのインストール、IDEの設定、そして最初のプロジェクト作成まで無事に完了しました。  
ここからは、Avaloniaの基本的な概念と機能について学んでいきましょう。  
デフォルトのAvaloniaテンプレートを「温度変換アプリ」へと作り替えることで、Avaloniaの基本を学びます。

このチュートリアルに沿ってアプリを作成することで、以下の内容について学ぶことができます。

{{< cards >}}

{{< card
    link="/docs/getting-started/starter-tutorial/"
    title="コントロールの追加"
    subtitle="アプリにボタンを追加し、ウィンドウ内に配置"
>}}

{{< card
    link="/docs/getting-started/starter-tutorial/"
    title="レイアウトの追加"
    subtitle="レイアウトコントロールを使用し、画面上の複数のコントロールを配置"
>}}

{{< card
    link="/docs/getting-started/starter-tutorial/"
    title="Avaloniaウィンドウのカスタマイズ"
    subtitle="ウィンドウのサイズ、タイトル、その他の属性を調整"
>}}

{{< card
    link="/docs/getting-started/starter-tutorial/"
    title="イベントとレスポンスの構築"
    subtitle="ボタンのクリックに対応するイベントハンドラーを作成"
>}}

{{< card
    link="/docs/getting-started/starter-tutorial/"
    title="データの変換"
    subtitle="ボタンがクリックされたとき、コードビハインドを使用して温度の値を変換"
>}}

{{< card
    link="/docs/getting-started/starter-tutorial/"
    title="演習"
    subtitle="3つのコーディング課題を通して、Avaloniaの理解度を確かめる"
>}}

{{< /cards >}}

![IDE Setup](https://docs.avaloniaui.net/assets/images/temperature-converter-complete-03158c752845ae81f0343e4d463b0cd8.png)

## .axaml
プロジェクトのディレクトリ内に、拡張子が ``.axaml`` で終わるファイルがあることに気づきましたか？  
これは「Avalonia XAML」の略であり、標準的なXAMLファイルとAvaloniaのファイルを区別するために、Avaloniaが独自に使用しているファイル拡張子です。

## XAMLライブプレビューの動作確認
Visual StudioまたはJetBrains RiderにAvaloniaをインストールしたばかりで、IDEでの開発にあまり慣れていない場合は、このタイミングでXAMLライブプレビュー機能が使用できるか確認しておくと良いでしょう。  

プレビュー機能を有効にする方法については、 [XAML live preview](https://docs.avaloniaui.net/docs/app-development/xaml-preview-and-design-settings)を参照してください。

## main windowファイルを開く
プロジェクトディレクトリの ``Views`` フォルダ内にある ``MainWindow.axaml`` ファイルを開きます。  
このチュートリアルでは、主にこのファイルを編集していきます。

![IDE Setup](https://docs.avaloniaui.net/assets/images/mainwindow-file-location-f67911ff0ad9dbf064087943d8dcb2c2.png)

``MainWindow.axaml`` 内のほぼすべての要素は、``<Window>...</Window>`` というXAMLタグの間に配置されます。  
このタグはAvaloniaのウィンドウを表し、ターゲットとなるプラットフォーム上でアプリが実行される際の「画面（ウィンドウ）」そのものとなります。  
Avaloniaのウィンドウをカスタマイズする方法については、[Avaloniaウィンドウのカスタマイズ](/docs/getting-started/starter-tutorial/)で詳しく解説します。  
アプリにボタンを追加する方法を学ぶには、このチュートリアルの[次のページへ](/docs/getting-started/starter-tutorial/adding-a-control/)進んでください。