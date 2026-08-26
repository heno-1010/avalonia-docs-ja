---
weight: 3
---
# イベントとレスポンスの構築
温度変換アプリは、見た目としては十分に機能しそうな状態になりましたが、まだ何も動作していません。次に必要なのは、「計算（Calculate）」ボタンが、クリックなどのユーザー操作に応答できるようにすることです。

## コードビハインドを使用したイベントハンドラーの作成
XAMLファイルは、C#のソースファイルと関連付けることができます。このファイルには、ボタンのイベント処理コードを記述します。この仕組みは「コードビハインド」と呼ばれます。

1. IDEでプロジェクトディレクトリを開き、**Views → MainWindow.axaml → MainWindow.axaml.cs** を参照します。これは、メインウィンドウのXAMLに対応するC#ソースファイルです。

![Temperature Converter](https://docs.avaloniaui.net/assets/images/mainwindow-codebehind-location-27ab6a5285a425b2a0506feab04399d3.png)
2. **MainWindow.axaml.cs**を開く  
3. まず、ファイルの先頭にある ``using`` ディレクティブを確認してください。  
この時点では、``using Avalonia.Controls;`` という1行だけが存在しているはずです。以下の 2 つの ``using`` ディレクティブを追加します。
```
using Avalonia.Interactivity;
using System.Diagnostics;
```

4. ファイル内のさらに下の方にある ``public partial class MainWindow : Window`` という行を探します。  
このクラスには現在、メインウィンドウ用のコンストラクタである ``public MainWindow()`` のみが含まれています。コンストラクタの下に、次のコードを追加します。
```
private void Button_OnClick(object? sender, RoutedEventArgs e)
{
    Debug.WriteLine("Click!");
}
```

5. C#ファイルは次のようになっているはずです。
```
using Avalonia.Controls;
using Avalonia.Interactivity;
using System.Diagnostics;

namespace GetStartedApp.Views;

public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
    }
    
    private void Button_OnClick(object? sender, RoutedEventArgs e)
    {
        Debug.WriteLine("Click!");
    }
}
```

6. XAMLファイルの``MainWindow.axaml``を開いてください。
7. ファイルの下の方にある``<Button>``を探してください。
8. ``<Button>`` タグに ``Click`` 属性を追加し、``Button_OnClick`` に関連付けてください。次のようにします。
```
<Button HorizontalAlignment="Center" Click="Button_OnClick">Calculate</Button>
```

## イベントハンドラーが正常に動作することを確認
イベントハンドラーが正しく作成されていることを確認するために、``Calculate``ボタンをクリックしたときに、デバッグ出力に「Click!」と表示されているか確認します。

{{< tabs items="Visual Studio, Rider" >}}

{{< tab name="Visual Studio" >}}
1. デフォルトでは分割ビューの下にある**Output**ウィンドウを開き、**Show output from:** のドロップダウンメニューから**Debug**を選択
2. アプリを実行
3. 実行中のアプリ画面で、**Calculate**ボタンを何度かクリック
4. **Output**ウィンドウに「Click!」と表示される
![](https://docs.avaloniaui.net/assets/images/vs-debug-output-click-a209fc02507a08a74bf7d4c0227bf4a2.png)
次のページでは、摂氏の温度を華氏に変換する計算式を実装する方法を学びます。

{{< /tab >}}

{{< tab name="Rider" >}}
1. GetStartedApp をデバッグモードで実行
![](https://docs.avaloniaui.net/assets/images/rider-run-debug-mode-4a4de5d2ea4ff03bbca29520aba66747.png)
2. 画面下部のパネルにある**Debug Output**タブを開く
3. 実行中のアプリ画面で**Calculate**ボタンを何度かクリック
4. Riderのデバック出力に「Click!」と表示される

次のページでは、摂氏の温度を華氏に変換する計算式を実装する方法を学びます。
{{< /tab >}}

{{< /tabs >}}