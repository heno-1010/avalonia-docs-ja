---
weight: 6
---
# Exercises
温度変換アプリを作成したので、Avaloniaについての理解度を確認するために、次の3つの演習に挑戦してみましょう。

## 演習1：既存の属性を変更する
**難易度：★**  
**GetStartedApp** のグリッド線を見えないようにしてください。

<details>
<summary>ヒント</summary>

MainWindow.axaml で ``<Grid>`` を指定しました。

</details>
　
<details>
<summary>解答</summary>

**MainWindow.axaml** で ``<Grid>`` の開始タグを探します。
``ShowGridLines`` 属性を ``False`` に変更してください。
```
<Grid ShowGridLines="False" Margin="5" 
  ColumnDefinitions="120, 100"
  RowDefinitions="Auto, Auto, Auto">
```

</details>

## 演習2：新しい属性を追加する
**難易度：★★**  
**GetStartedApp** の Fahrenheit（華氏）のテキストボックスに、ユーザーが文字を入力できないようにしてください。

<details>
<summary>ヒント①</summary>

TextBox コントロールについて詳しく知るには、[TextBoxのAPIリファレンス](https://docs.avaloniaui.net/api/avalonia/controls/textbox)を確認してください。

</details>

<details>
<summary>ヒント②</summary>

[TextBoxのAPIリファレンス](https://docs.avaloniaui.net/api/avalonia/controls/textbox)を見ると、``IsReadOnly`` という属性があります。

</details>
　
<details>
<summary>解答</summary>

**MainWindow.axaml** でFahrenheit（華氏）のボックスに対応する ``<TextBox>`` タグを探します。
``IsReadOnly`` 属性を追加し、その値を ``True`` に設定してください。
```
<TextBox Grid.Row="1" Grid.Column="1" Margin="0 5" Text="0" Name="Fahrenheit" IsReadOnly="True"/>
```

</details>

## 演習3：新しいイベント処理をプログラムする
**難易度：★★★**  
ユーザーが入力するたびに、**GetStartedApp** が温度変換を計算するようにしてください。

<details>
<summary>ヒント①</summary>

TextBox コントロールについて詳しく知るには、[TextBoxのAPIリファレンス](https://docs.avaloniaui.net/api/avalonia/controls/textbox)を確認してください。

</details>

<details>
<summary>ヒント②</summary>

[TextBoxのAPIリファレンス](https://docs.avaloniaui.net/api/avalonia/controls/textbox)を見ると、``TextChanged`` というイベントがあります。

</details>

<details>
<summary>ヒント③</summary>

イベントハンドラーは、C# のコードビハインドである **MainWindow.axaml.cs** に定義されています。  
また、XAML ファイルである **MainWindow.axaml** からも参照されています。

</details>
　
<details>
<summary>解答</summary>

1. **MainWindow.axaml** でCelsius（摂氏）のボックスに対応する ``<TextBox>`` タグを探します。
``TextChanged`` イベントを追加し、その値を ``Celsius_TextChanged`` などのイベント名を指定してください。
```
<TextBox Grid.Row="0" Grid.Column="1" Margin="0 5" Text="0" TextChanged="Celsius_TextChanged" Name="Celsius"/>
```

2. **MainWindow.axaml** で ``<Button>`` から始まる行全体を削除してください。  
この行はもう必要ありません。  
~~`<Button HorizontalAlignment="Center" Click="Button_OnClick">Calculate</Button>`~~

3. **MainWindow.axaml** で ``private void`` から始まるイベントハンドラーの行を探します。
イベント名を ``Button_OnClick`` から、XAML ファイルで付けた名前に変更してください。  
（例：``Celsius_TextChanged`` ）
```
private void Celsius_TextChanged(object? sender, RoutedEventArgs e)
```
4. アプリを実行して、Celsius（摂氏）のボックスに入力すると、Fahrenheit（華氏）のボックスの値が変化することを確認してください。
</details>

<details>
<summary>オプション：さらなる改善</summary>

Celsius（摂氏）の入力欄で、空欄やマイナス記号（-）だけの入力も受け付けるようにするには、コードビハインドを次のように変更します。

1. **MainWindow.axaml.cs** で、イベントハンドラー ``private void Celsius_TextChanged`` を探します。空欄またはマイナス記号（-）だけの状態を受け付けるための ``if`` 条件を追加します。
```
if (string.IsNullOrEmpty(Celsius.Text) || Celsius.Text == "-")
    {
        Fahrenheit.Text = "";
    }
```

2. 元の double のパーサー部分を ``else if`` から始まる条件に変更します。これが2番目の条件になります。
```
else if (double.TryParse(Celsius.Text, out double C))
```

3. イベントハンドラーは、次のようになります。
```
private void Celsius_TextChanged(object? sender, RoutedEventArgs e)
{
    if (string.IsNullOrEmpty(Celsius.Text) || Celsius.Text == "-")
    {
        Fahrenheit.Text = "";
    }
    else if (double.TryParse(Celsius.Text, out double C))
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

4. アプリを実行し、摂氏の入力欄の内容をすべて削除したり、マイナス記号（-）だけを入力したりしても、入力欄が 0 に戻らないことを確認します。この状態では、華氏の入力欄には何も表示されません。  
この変更により、途中で入力内容がリセットされることなく、負の数を入力できるようになります。
</details>

お疲れさまでした！Avalonia の入門チュートリアルはこれで完了です。

## さらに詳しく学ぶ
- 次のチュートリアルで [ToDo リストアプリ](https://github.com/AvaloniaUI/Avalonia.Samples/tree/main/src/Avalonia.Samples/CompleteApps/SimpleToDoList)を作ってみる
- Avalonia の[基本](https://docs.avaloniaui.net/docs/fundamentals/avalonia-xaml)を学ぶ
- [MVVM デザインパターン](https://docs.avaloniaui.net/docs/fundamentals/the-mvvm-pattern)を理解する
- UI の[スタイル設定](https://docs.avaloniaui.net/docs/styling/styles)について学ぶ
- Avalonia の[コントロール一覧](https://docs.avaloniaui.net/controls)を見る
- [API リファレンス](https://docs.avaloniaui.net/api)を見る