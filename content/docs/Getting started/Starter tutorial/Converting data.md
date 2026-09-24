---
weight: 6
---
# データの変換
温度変換アプリを完成させるために、数値を入力として受け取り、指定した計算式を使って別の数値に変換する機能を追加する必要があります。

## コントロールに名前を付ける
アプリ内のコントロールを区別するために、コントロールに名前を付けることができます。ここでは、``TextBox`` コントロールに名前を付けます。

1. アプリが実行中であれば停止
2. **MainWindow.axaml**ファイルで、Celsius のテキストボックスを探します。:  
``<TextBox Grid.Row="0" Grid.Column="1" Margin="0 5" Text="0"/>``
3. ``<TextBox>``タグに``Name``属性を追加します。次のようにしてください。:  
```
<TextBox Grid.Row="0" Grid.Column="1" Margin="0 5" Text="0" Name="Celsius"/>
```
4. 華氏のテキストボックスを見つけます:  
``<TextBox Grid.Row="1" Grid.Column="1" Margin="0 5" Text="0"/>``
5. ``<TextBox>``タグに``Name``属性を追加します。次のようにしてください。:  
```
<TextBox Grid.Row="1" Grid.Column="1" Margin="0 5" Text="0" Name="Fahrenheit"/>
```

## 入力値を取得する
次に、アプリから摂氏のテキストボックスに入力された値にアクセスできるようにします。
1. **MainWindow.axaml.cs**ファイルで、[先ほど作成](../establishing-events-and-responses/)した``Button_OnClick``イベントハンドラーを見つけます。
2. ``Debug``ステートメントを変更して、摂氏のテキストボックスに入力されたテキストを表示するようにします。  
次のようにしてください。:  
```
Debug.WriteLine($"Click! Celsius={Celsius.Text}");
```
3. [IDEで必要な場合はデバッグモード](../establishing-events-and-responses/)にして、アプリをもう一度実行します。
4. **Calculate**ボタンを何度かクリックしてみてください。
5. 摂氏テキストボックス内の数値を変更し、**Calculate**ボタンをもう何回かクリックしてください。
6. デバッグ出力に摂氏のテキストボックスに入力した値が表示されていることを確認してください。

## 変換式を実装する
最後のステップでは、摂氏の値を華氏に変換する計算式をアプリに組み込み、計算結果を華氏のテキストボックスに表示するようにプログラムします。

摂氏から華氏への変換式は、次のとおりです。
> **Fahrenheit = Celsius * (9/5) + 32**

C# のコードビハインドで、この処理を実装する方法は次のとおりです。

1. **MainWindow.axaml.cs**で、[先ほど作成](../establishing-events-and-responses/)した``Button_OnClick``イベントハンドラーを見つけてください。
2. ``Debug``ステートメントを削除してください。
3. （任意）ファイルの先頭にある ``using System.Diagnostics;`` ステートメントも削除できます。もう必要ありません。
4. 摂氏の入力値が数値であることを検証するため、``Button_OnClick`` イベントハンドラー内に次のコードを追加してください。
```
if (double.TryParse(Celsius.Text, out double C))
```
5. ``if``条件文の中に、変換式を適用するための次のコードを追加してください。
```
{
    var F = C * (9d / 5d) + 32;
```
6. 次のコードを追加して、計算結果をテキストとして華氏のテキストボックスに表示します。その後、条件文を閉じてください。
```
    Fahrenheit.Text = F.ToString("0.0");
}
```
7. 無効な入力があった場合に、テキストボックスを 0 にリセットするため、``else`` 条件節を追加してください。
```
else
{
    Celsius.Text = "0";
    Fahrenheit.Text = "0";
}
```
8. 完成したイベントハンドラーは、次のようになります。
```
private void Button_OnClick(object? sender, RoutedEventArgs e)
{
    if (double.TryParse(Celsius.Text, out double C))
    {
        var F = C * (9d / 5d) + 32;
        Fahrenheit.Text = F.ToString("0.0");
    }
    else
    {
        Celsius.Text = "0";
        Fahrenheit.Text = "0";
    }
}
```

## 作業内容を確認する
1. **GetStartedApp**を実行してください。
2. 次の数値を摂氏のボックスに入力してから、**Calculate**をクリックし、アプリが正しい華氏の値を返すことを確認してください。
| Celsius | Fahrenheit |
|---|---|
| -10 | 14.0 |
| 0 | 32.0 |
| 10 | 50.0 |
| 21 | 69.8 |
| 32.0 | 89.6 |
3. 摂氏のボックスは変更せずに、華氏のボックスに何か入力してください。**Calculate**をクリックして、華氏のボックスのテキストが指定した摂氏の値に対応する計算結果に戻ることを確認してください。
4. 摂氏のボックスに「abc」と入力し、アプリによって両方のテキストボックスが 0 にリセットされることを確認してください。
{{< callout type="warning" title="入力欄" >}}
華氏の入力欄には数値を入力できるのに、それを摂氏に変換できないのは、少し不思議ですよね。ご心配なく。次の演習では、この入力欄を読み取り専用にします。
{{< /callout >}}

おめでとうございます！Avalonia を使って温度変換アプリを作成しました。何よりも重要なのは、これで Avalonia フレームワークの基本をしっかり身につけたことです。  

これで、自分のアプリの開発を始める準備が整いました。  

3つの短い演習問題で知識を確認したい場合は、このチュートリアルの最後のページに進んでください。