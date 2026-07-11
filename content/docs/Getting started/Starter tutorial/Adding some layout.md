---
weight: 3
---
# レイアウトの追加
現時点で、温度変換アプリには、ウィンドウの中央にボタンが1つ配置されています。  
各Avaloniaウィンドウでは、コンテンツ領域に配置できるコントロールは1つだけのため、これ以上要素を追加することはできません。（レイアウト領域についての詳しい説明は次のページ「Controls reference page」で扱います。）  
ウィンドウ内に複数のUI要素を配置するには、**レイアウトコントロール**を使用する必要があります。  
レイアウトコントロールについての詳しい情報は、[Layout controls](https://docs.avaloniaui.net/controls)を参照してください。

## StackPanelの挿入
StackPanel レイアウトコントロールを使用すると、ボタンの上にテキストを配置できます。

1. **MainWindow.axaml** ファイル内で、Buttonを``<StackPanel>...</StackPanel>``で囲んでください。
```
<StackPanel>
	<Button>Calculate</Button>
</StackPanel>
```
2. ボタンの上に``TextBlock``を追加してください。  
（デフォルトの **MainWindow.axaml** にあった ``TextBlock`` タグを思い出すかもしれません。これはウィンドウ内にテキストを表示するものです。）  
``TextBlock`` の属性を次のように設定してください。
- Margin="5"
- FontSize="24"
- HorizontalAlignment="Center"
- Text="Temperature Converter"

```
<StackPanel>
    <TextBlock Margin="5"
               FontSize="24" 
               HorizontalAlignment="Center"
               Text="Temperature Converter">
    </TextBlock>

    <Button HorizontalAlignment="Center">Calculate</Button>
</StackPanel>
```

3. アプリを実行するか、プレビューアーで確認してください。  
「Temperature Converter」という文字が、「Calculate」ボタンの上に表示されているはずです。
![Temperature Converter](https://docs.avaloniaui.net/assets/images/temperature-converter-text-only-47a9bf06b79989bd4368fdf55460d9d4.png)

4. ``TextBlock`` を ``<Border>...</Border>`` タグで囲み、``Border`` の属性を次のように設定してください。
- Margin="5"
- CornerRadius="10"
- Background="LightBlue"

```
<StackPanel>
    <Border Margin="5" CornerRadius="10" Background="LightBlue">
        <TextBlock Margin="5"
                   FontSize="24" 
                   HorizontalAlignment="Center"
                   Text="Temperature Converter">
        </TextBlock>
    </Border>

    <Button HorizontalAlignment="Center">Calculate</Button>
</StackPanel>
```

5. アプリを実行するか、プレビューアーで確認してください。  
「Temperature Converter」という文字が、角の丸い青い枠（ボックス）の中に表示されているはずです。
![Temperature Converter](https://docs.avaloniaui.net/assets/images/temperature-converter-blue-border-85016c962da4c300f410b2bb07adc855.png)

{{< callout type="tip" title="Temperature Converter" >}}
``StackPanel``はデフォルトだと、要素を縦方向（垂直）に並べます。  
``Orientation`` 属性を ``Horizontal`` に設定すると、横方向（水平方向）に並べることができます。
{{< /callout >}}

## Gridの挿入
次は、Grid レイアウトコントロールを追加します。Gridは、行と列で構成されたセルを作成し、そのセルの中に様々なコントロールを配置できるレイアウトです。
1. アプリが実行中であれば停止
2. **MainWindow.axaml** ファイル内で、Buttonを``</Border>``と``<Button>``の間に、``<Grid>...</Grid>``タグを挿入してください。
```
<StackPanel>
    <Border Margin="5" CornerRadius="10" Background="LightBlue">
        <TextBlock Margin="5"
            HorizontalAlignment="Center"
            FontSize="24"
            Text="Temperature Converter">
        </TextBlock>
    </Border>
    <Grid ShowGridLines="True" Margin="5" 
          ColumnDefinitions="120, 100"
          RowDefinitions="Auto, Auto">
    </Grid>
    <Button HorizontalAlignment="Center">Calculate</Button>
</StackPanel>
```
ここでは、``Gird``にいくつかの属性を設定しています。
- 2列2行
- グリッド線の表示
- セルの高さは内容に合わせて自動的に調整  
空のセルの高さは自動設定では0になるため、現在はGirdが水平な一本線として表示される
![Temperature Converter](https://docs.avaloniaui.net/assets/images/temperature-converter-empty-grid-aeb17bff021cec2752962e88e448a48b.png)

## Gridにコントロールを配置
1. ``Grid.Row`` と ``Grid.Column`` 属性で対象のセルを指定し、``Grid`` の左側のセルに ``TextBlock`` コントロールを配置、「Celsius」と「Fahrenheit」を表示します。

{{< callout type="tip" title="Temperature Converter" >}}
``Grid``の行や列の番号は0から始まります。最初のセルは0番として扱われます。
{{< /callout >}}
```
        <Grid ShowGridLines="True" Margin="5" 
              ColumnDefinitions="120, 100"
              RowDefinitions="Auto, Auto">
            <TextBlock Grid.Row="0" Grid.Column="0" Margin="10">Celsius</TextBlock>
            <TextBlock Grid.Row="1" Grid.Column="0" Margin="10">Fahrenheit</TextBlock>
        </Grid>
```

2. 次に、``Grid.Row`` と ``Grid.Column`` 属性で対象のセルを指定し、``Grid`` の右側のセルに ``TextBox`` コントロールを配置します。  
``TextBox`` は、キーボードから文字を入力できる入力欄を作成するためのコントロールです。
```
        <Grid ShowGridLines="True" Margin="5" 
              ColumnDefinitions="120, 100"
              RowDefinitions="Auto, Auto">
            <TextBlock Grid.Row="0" Grid.Column="0" Margin="10">Celsius</TextBlock>
            <TextBox Grid.Row="0" Grid.Column="1" Margin="0 5" Text="0"/>
            <TextBlock Grid.Row="1" Grid.Column="0" Margin="10">Fahrenheit</TextBlock>
            <TextBox Grid.Row="1" Grid.Column="1" Margin="0 5" Text="0"/>
        </Grid>
```
 3. アプリを実行するか、プレビューアーで確認してください。  
 グリッド線で区切られたセル内に、追加したテキストと入力ボックスがウィンドウ上に表示されているはずです。
 ![Temperature Converter](https://docs.avaloniaui.net/assets/images/temperature-converter-filled-grid-8b9aa9fda86ac3ba2f2a4c8bef3244a7.png)
 次のページでは、アプリのウィンドウサイズを調整する方法を学びます。