---
weight: 3
---
# Avaloniaウィンドウのカスタマイズ
先ほど[説明](../)したように、Avaloniaウィンドウはターゲットプラットフォーム上でアプリが実行される領域です。  
.axamlファイルでは、``<Window>...</Window>``タグを使って、そのウィンドウ内に表示する内容を定義します。

## レイアウト領域
Avaloniaのウィンドウには、次の4つのレイアウト領域があります。  
① Margin（マージン）  
② Border（ボーダー）  
③ Padding（パディング）  
⑤ Content（コンテンツ）  
先ほど使用した``StackPanel``のような一部のレイアウトコントロールは、同じ4つのレイアウト領域を持つ、より小さなサブウィンドウを作成します。
{{< callout type="warning" title="コンテンツ領域に配置できるコントロール" >}}
Avaloniaの各ウィンドウでは、コンテンツ領域に配置できるコントロールは1つだけです。
{{< /callout >}}

## ウィンドウの既定の属性
コントロールと同様に、Avaloniaのウィンドウには、表示方法や動作を定義するXML属性があります。  
**MainWindow.axaml**を先頭までスクロールし、``<Window>``タグを確認してください。そこには、いくつかのデフォルト設定が記述されています。
```
<Window xmlns="https://github.com/avaloniaui"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:vm="using:GetStartedApp.ViewModels"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d" d:DesignWidth="800" d:DesignHeight="450"
        x:Class="GetStartedApp.Views.MainWindow"
        x:DataType="vm:MainWindowViewModel"
        Icon="/Assets/avalonia-logo.ico"
        Title="GetStartedApp">
```
{{< callout type="warning" title="XML名前空間" >}}
``<Window>``タグの初めの数行では、Avaloniaで使用されるXML名前空間が宣言されています。  
使用されている名前空間のエイリアスは``x``,``vm``,``d``,``mc``です。
{{< /callout >}}

## ウィンドウの属性を設定
ウィンドウのサイズを調整して、横向き（ランドスケープ）ではなく縦向き（ポートレート）で表示できるようにしてみましょう。これは、アプリ開発時に、モバイル端末での表示を確認する際によく行われる操作です。
### プレビュー画面のサイズを設定
``d:DesignWidth``と``d:DesignHeight``の値を変更すると、実行時にウィンドウには影響を与えず、ライブプレビュー上でのアプリの表示サイズだけを変更できます。
1. **MainWindow.axaml**を開き、``<Window>...</Window>``タグ内にある次の行を見つけてください。
```
mc:Ignorable="d" d:DesignWidth="800" d:DesignHeight="450"
```
2. ``d:DesignWidth``を``400``に設定
3. プレビュー画面を確認してください。プレビューがモバイル端末の表示に近い状態になっていることが確認できます。

詳しくは、[previewing your UI design](https://docs.avaloniaui.net/docs/app-development/xaml-preview-and-design-settings)を参照してください。

![Temperature Converter](https://docs.avaloniaui.net/assets/images/temperature-converter-portrait-orientation-933867e63d9c915fd3f6ca54a598d20b.png)

### 実行時のウィンドウサイズを設定
実行時のアプリウィンドウのサイズを調整するには、``<Window>``の開始タグに``Width``属性と``Height``属性を追加する必要があります。  
1. **MainWindow.axaml**を開き、``<Window>``の開始タグの最後の行に移動してください。
```
Title="GetStartedApp">
```
2. その行の下に、属性``Width="400"``と``Height="450"``を追加してください。  
山かっこ（>）を最後に移動して``<Window>``開始タグが正しく閉じられるようにしてください。
```
Title="GetStartedApp"
Width="400"
Height="450">
```
3. アプリを実行してください。アプリのウィンドウがモバイル端末の表示に近い形になっていることを確認できます。
{{< callout type="warning" title="ウィンドウのサイズ調整" >}}
多くのモバイルプラットフォームでは、実際にはウィンドウサイズの指定は無視され、画面に合わせてウィンドウが自動的にサイズ調整されます。開発時に、対象となる各プラットフォームごとに個別のサイズを設定する必要はありません。
{{< /callout >}}


次のページでは、ボタンがクリックに反応するように、イベント処理を作成する方法を学びます。