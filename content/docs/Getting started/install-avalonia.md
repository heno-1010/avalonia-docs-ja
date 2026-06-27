---
weight: 1
---
# Avaloniaのインストール
コマンドラインやIDEでAvaloniaアプリケーションを作成できるようにするため、.NET SDKとAvaloniaプロジェクトテンプレートをインストールしてください。

## 前提条件
Avaloniaをインストールする前に以下の環境が整っていることを確認してください。
- .NET 8.0以降（2025年10月時点）

.NETがインストールされていない場合は、[.NETの公式サイト](https://dotnet.microsoft.com/en-us/download/dotnet)からダウンロードし、お使いのオペレーションシステム向けのインストール手順に従ってください。 

インストールが正しく行われたかどうかは、次のコマンドを実行して確認できます。
```
dotnet --version
```
出力結果に8.0以上のバージョン番号が表示されれば、インストールは正常に完了しています。  
もし「コマンドが認識されません」（またはそれに類するメッセージ）などが表示される場合は、.NET SDKのインストールディレクトリがシステムのPATH環境変数に追加されていることを確認してください。

{{< callout type="tip" title="複数の.NETバージョン" >}}
同じコンピューターに複数のバージョンの .NET SDK をインストールできます。
Avaloniaでは.NET 8.0以降が必要ですが、必要に応じてマルチターゲット機能を利用することで、以前の .NET バージョン向けにもプロジェクトをビルドできます。  
インストールされている .NET SDK のバージョンを確認するには、次のコマンドを実行してください。  
``dotnet --list-sdks``
{{< /callout >}}

## Avaloniaテンプレートのインストール
Avalonia は、新しいプロジェクトを作成するために標準の .NET テンプレートを使用します。次のコマンドを実行してインストールしてください。
```
dotnet new install Avalonia.Templates
```
インストールが完了すると、テンプレートが正常にインストールされたことを示すメッセージが表示されます。
```
Template Name                                 Short Name                  Language    Tags
--------------------------------------------  --------------------------  ----------  ---------------------------------------------------------
Avalonia .NET App                             avalonia.app                [C#],F#     Desktop/Xaml/Avalonia/Windows/Linux/macOS
Avalonia .NET MVVM App                        avalonia.mvvm               [C#],F#     Desktop/Xaml/Avalonia/Windows/Linux/macOS
Avalonia Cross Platform Application           avalonia.xplat              [C#],F#     Desktop/Xaml/Avalonia/Browser/Mobile
Avalonia Resource Dictionary                  avalonia.resource                       Desktop/Xaml/Avalonia/Windows/Linux/macOS
Avalonia Styles                               avalonia.styles                         Desktop/Xaml/Avalonia/Windows/Linux/macOS
Avalonia TemplatedControl                     avalonia.templatedcontrol   [C#],F#     Desktop/Xaml/Avalonia/Windows/Linux/macOS
Avalonia UserControl                          avalonia.usercontrol        [C#],F#     Desktop/Xaml/Avalonia/Windows/Linux/macOS
Avalonia Window                               avalonia.window             [C#],F#     Desktop/Xaml/Avalonia/Windows/Linux/macOS
```

{{< callout type="tip" title="ヒント" >}}
いつでも、次のコマンドを実行することで、インストールされているテンプレートを確認できます。  
``dotnet new list``  
コマンドの出力の中から、名前に 「Avalonia」 が含まれている項目を探してください。
{{< /callout >}}

### 既存テンプレートの更新
以前にテンプレートをインストールしている場合は、次のコマンドで最新バージョンに更新できます。  
これにより、Avalonia.Templatesを含む、インストール済みのすべてのテンプレートパッケージを更新します。
```
dotnet new update
```  

特定のテンプレートバージョン（例えば特定のAvaloniaリリースに合わせたい場合）をインストールしたいときは、バージョンを明示的に指定してください。
```
dotnet new install Avalonia.Templates@12.0.2
```

### テンプレートのアンインストール
Avaloniaテンプレートを削除して最初からやり直したい場合は、次のコマンドを実行してください。
```
dotnet new uninstall Avalonia.Templates
```
その後、前述の dotnet new install コマンドを使用して、再度インストールしてください。
{{< callout type="warning" title="Note" >}}
Visual Studio用のAvalonia拡張機能をインストールすると、テンプレートは自動的に含まれます。  
そのため、別のIDEを使用している場合や、コマンドラインから利用したい場合にのみ、``dotnet new install`` を実行する必要があります。
{{< /callout >}}

## インストールの確認
正しくインストールされているか確認するために、簡単なテストプロジェクトを作成します。
```
dotnet new avalonia.app -o TestApp
cd TestApp
dotnet build
```
ビルドが成功すれば、インストールは正常に完了しています。  
確認が終わったら、``TestApp`` フォルダーは削除しても構いません。

### よくある問題
- **``dotnet new``にAvaloniaテンプレートが表示されない場合**  

``dotnet new install Avalonia.Templates``を実行していること、およびコマンドがエラーなく完了していることを確認してください。
その後、ターミナルを再起動し、再度お試しください。

- **SDKが見つからないことによるビルドエラー**  

``dotnet --version``を実行し、.NET 8.0 以上が表示されることを確認してください。  
また、親ディレクトリにある``global.json``により古い SDK が既定として使用されている場合は、そのファイルを削除するか、互換性のある SDK バージョンを指定してください。

- **macOSやLinuxでの権限エラー**

インストールコマンドで権限エラーが発生する場合は、sudo を使用せずに実行してください。
.NET のテンプレートエンジンはユーザープロファイルディレクトリにテンプレートをインストールするため、管理者権限は不要です。