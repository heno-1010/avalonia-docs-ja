---
weight: 3
---
# コントロールの追加
Avaloniaのコントロールとはユーザーが表示したり操作したりできるUI要素全般を指します。  
例えば、
- ボタン
- スライダー
- チェックボックス
- テキストボックス
- メニュー  
などがその例です。  

それぞれのコントロールは、AXAMLマークアップ内でXML要素として表現されます。  
そのため、ユーザーインターフェースの要素を追加したり削除したり、並べ替えたりすることが簡単になります。

組み込みコントロールの完全な一覧については、[Controls reference page](https://docs.avaloniaui.net/controls)を参照してください。  

## ボタンの挿入
まず、アプリに最初から表示されているテキストを、``Button``に置き換えます。

1. アプリが実行中であれば停止
2. ``MainWindow.axaml``ファイル内で、次の行を見つけてください。
```
<TextBlock Text="{Binding Greeting}" HorizontalAlignment="Center" VerticalAlignment="Center"/>
```
3. その行全体を次の要素に置き換えてください
```
<Button>Calculate</Button>
```

開始タグ（``<Button>``）と終了タグ（``</Button>``）の間にあるテキストが、ボタンに表示されるラベルになります。  
この場合、ボタンには「Calculate」と表示されます。

4. アプリを実行するか、プレビューアーで確認してください。  
アプリのウィンドウにCalculateボタンが表示されるはずです。
5. ボタンにマウスカーソルを合わせたりクリックしたりして、見た目がどのように変化するか試してみてください。
Avaloniaのデフォルトテーマには、ホバー・押下・フォーカス時の視覚的な状態があらかじめ用意されているため、追加コードを書かなくてもボタンはユーザーの操作に応じて見た目が変化します。
![Insert a button](https://docs.avaloniaui.net/assets/images/calculate-button-left-e5acb6ead7a254fdb1c6710f872628df.png)

## ボタンの属性を設定
Avaloniaのコントロールは、表示や動作を設定するために、XML属性を使用します。  
属性は、サイズ・位置・色などを制御するためにAXAMLのマークアップ内で適用する設定です。

現在、Calculate ボタンはウィンドウの左端に揃えられています。  
これは、``HorizontalAlignment`` 属性の既定値が ``Left`` に設定されているためです。ボタンを中央に配置するには、この属性を明示的に設定する必要があります。

1. ``MainWindow.axaml``ファイル内で、次の行を見つけてください。
```
<Button>Calculate</Button>
```
2. ``<Button>`` タグに ``HorizontalAlignment`` 属性を追加し、その値を ``Center`` に設定してください。
```
<Button HorizontalAlignment="Center">Calculate</Button>
```
3. アプリを実行するか、プレビューアーで確認してください。  
Calculateボタンがウィンドウの中央に移動するのが見えるはずです。
![Insert a button](https://docs.avaloniaui.net/assets/images/calculate-button-center-061ca7c128f434efbd27bc7540771c97.png)

{{< callout type="tip" title="VerticalAlignment" >}}
``VerticalAlignment`` を設定して、コントロールが縦方向のどの位置に配置されるかを制御することもできます。
ボタンに ``VerticalAlignment="Center"`` を設定して、その効果を確認してみてください。
{{< /callout >}}

## 今回学んだ内容
このセクションでは、以下のことを学びました。
- AXAML マークアップを記述してウィンドウに Button コントロールを追加
- 開始タグと終了タグの間にボタンのコンテンツ（ラベルの文字）を設定
- HorizontalAlignment 属性を使ってボタンの位置を変更

次のページでは、レイアウトコントロールを使ってアプリに複数の要素を追加する方法を学びます。