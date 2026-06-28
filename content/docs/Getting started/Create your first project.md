---
weight: 3
---
# 最初のプロジェクトを作成
お好みのIDEまたはコマンドラインを使って、MVVMテンプレートを利用した最初のAvaloniaアプリケーションを作成し、実行してみましょう。  
このガイドでは、テンプレートから新しいAvaloniaアプリを作成し、実際に実行するまでの手順を説明します。ガイドを終える頃には、Avaloniaで作成したアプリケーションのウィンドウが画面に表示されるようになります。

## プロジェクトを作成
最初のプロジェクトでは、Model-View-ViewModel（MVVM）テンプレートを使用します。  
このテンプレートは、MVVMパターンに基づいたプロジェクトを作成します。  
MVVMは、Avaloniaアプリケーションを開発する際に推奨されている設計パターンです。

{{< tabs items="Visual Studio,Visual Studio Code,Rider,Command line" >}}

{{< tab name="Visual Studio" >}}
1. Visual Studioで、**ファイル → 新規作成 → プロジェクト/ソリューション** をクリック
2. 検索ボックスに Avalonia と入力
3. 検索結果から **Avalonia .NET MVVM App** を選択。  
複数の選択肢が表示される場合はC#向けのものを選び、**次へ** をクリック
4. プロジェクト名を 「GetStartedApp」 に設定
5. 必要に応じて保存先（ターゲットディレクトリ）を変更し、次へ をクリック
6. 使用する**.NET**のバージョンをフレームワークとして選択
7. ターゲットプラットフォームを選択する画面が表示された場合は、**Desktop** を選択
8. **作成** をクリック
{{< /tab >}}

{{< tab name="Visual Studio Code" >}}
1. Visual Studio Codeで、コマンドパレットを開き、Windowsでは ``Ctrl + Shift + P``、macOSでは ``⌘ + Shift + P`` を押す
2. 検索ボックスに .NET と入力
3. 検索結果から **.NET: New Project...** を選択
4. プロジェクトテンプレートの一覧から **Avalonia MVVM App** を選択
5. プロジェクトを保存するディレクトリを指定
6. プロジェクト名を 「GetStartedApp」 に設定
7. **Create project** をクリック
{{< /tab >}}

{{< tab name="Rider" >}}
1. Riderのスタート画面で **New Solution** を選択
2. サイドバーで下にスクロールし、Custom Templatesの中から **Avalonia .NET MVVM App** を選択
3. ソリューション名を 「GetStartedApp」 に設定
4. **Create** をクリック
{{< /tab >}}

{{< tab name="Command line" >}}
次のコマンドを実行
```
dotnet new avalonia.mvvm -o GetStartedApp
```
新しく作成された**「GetStartedApp」**という名前のフォルダを確認してください。その中に、新しいプロジェクトファイルが含まれています。
{{< /tab >}}

{{< /tabs >}}

## プロジェクトを実行
{{< tabs items="Visual Studio,Visual Studio Code,Rider,Command line" >}}

{{< tab name="Visual Studio" >}}
上部ツールバーで、実行ボタンの横にある「GetStartedApp」を選択、その後、**Run（実行）** をクリックします。  
ソリューションがビルドされ、アプリが新しいウィンドウで起動します。  
デフォルトでは、「Welcome to Avalonia!」という文字列が表示されるようになっています。
![IDE Setup](https://docs.avaloniaui.net/assets/images/welcome-to-avalonia-2631137465e12ec00f3157f4f4d756b8.png)
{{< /tab >}}

{{< tab name="Visual Studio Code" >}}
1. サイドナビゲーションバーで **Run and Debug（実行とデバッグ）** を選択
2. デバッガーの選択を求められた場合は、**C#** を選択
3. **Run and Debug** をクリック
![IDE Setup](https://docs.avaloniaui.net/assets/images/welcome-to-avalonia-2631137465e12ec00f3157f4f4d756b8.png)
{{< /tab >}}

{{< tab name="Rider" >}}
上部ツールバーで **Run（実行）** をクリックしてください。  
ソリューションがビルドされ、アプリが新しいウィンドウで起動します。デフォルトでは、「Welcome to Avalonia!」という文字列が表示されます。
![IDE Setup](https://docs.avaloniaui.net/assets/images/welcome-to-avalonia-2631137465e12ec00f3157f4f4d756b8.png)
{{< /tab >}}

{{< tab name="Command line" >}}
**「GetStartedApp」** プロジェクトがあるディレクトリに移動し、次のコマンドを実行
```
dotnet run
```
ソリューションがビルドされ、アプリが新しいウィンドウで起動します。デフォルトでは、「Welcome to Avalonia!」という文字列が表示されます。
![IDE Setup](https://docs.avaloniaui.net/assets/images/welcome-to-avalonia-2631137465e12ec00f3157f4f4d756b8.png)
{{< /tab >}}

{{< /tabs >}}

## プロジェクトに何が含まれていますか？
MVVMテンプレートは、次のような構成のプロジェクトを作成します。
| ファイル/フォルダ | 目的 |
|---|---|
| App.axaml | アプリケーション全体のリソースやスタイルを定義する。.axaml 拡張子は Avalonia XAML の略 |
| ViewModels/ | メインウィンドウのデータやロジックを保持する ``MainWindowViewModel`` が含まれている |
| Views/MainWindow.axaml | メインウィンドウの外観を定義するXAMLマークアップ |
| Views/MainWindow.axaml.cs |メインウィンドウのコードビハインドファイル |
| Program.cs |Avaloniaを構成し起動するアプリケーションのエントリーポイント |