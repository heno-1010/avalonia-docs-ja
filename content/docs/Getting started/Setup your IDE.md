---
linkTitle: "Set up your IDE"
weight: 2
---
# IDEのセットアップ
Avaloniaの開発用に、任意のIDEを設定してください。  
Visual Studio、Visual Studio Code、または JetBrains Rider 用の拡張機能をインストールします。

{{< tabs items="Visual Studio,Visual Studio Code,Rider" >}}

{{< tab name="Visual Studio" >}}
Windows で作業している場合、Visual Studio にAvalonia for Visual Studio拡張機能を導入することで、充実したXAMLの編集機能やプレビュー機能を利用できます。  
この拡張機能は、Visual Studio 2022 バージョン 17.12 以降をサポートしています。

Avalonia for Visual Studio拡張機能は、プロフェッショナル向け開発ツール群である [Avalonia Plus](https://avaloniaui.net/pricing) の一部です。

**Avalonia for Visual Studio のインストール方法**
1. Visual Studioで 拡張機能 →拡張機能の管理 を開く
2. 検索バーに「Avalonia」と入力
3. インストールをクリック
4. 追加のインストール手順に従う。  
インストールを完了するために、Visual Studioを再起動する必要がある場合があります。

![IDE Setup](https://docs.avaloniaui.net/assets/images/download-vs-avalonia-extension-38f26cb008fc76cf7cae9e1f748c9ece.png)

または、[Visual Studio Marketplaceから拡張機能をダウンロード](https://marketplace.visualstudio.com/items?itemName=AvaloniaTeam.AvaloniaVS)することもできます。  
機能や設定の詳細については、[Avalonia for Visual Studio](https://docs.avaloniaui.net/tools/visual-studio-extension)のページを参照してください。


古いバージョンの Visual Studio を使用している場合は、Marketplace から対応する旧バージョンの拡張機能をダウンロードする必要がある場合があります。たとえば [Visual Studio 2019 用のバージョン](https://marketplace.visualstudio.com/items?itemName=AvaloniaTeam.AvaloniaforVisualStudio)などです。

XAMLプレビュー機能の使用方法について詳しくは、[XAML live preview](https://docs.avaloniaui.net/docs/app-development/xaml-preview-and-design-settings)のページを参照してください。

{{< /tab >}}

{{< tab name="Visual Studio Code" >}}
Avalonia for Visual Studio Code拡張機能は、Visual Studio拡張機能と同じXAMLパーサーを基盤として構築されています。  
両方のIDEは同じ基盤エンジンを共有しているため、コード編集機能の改善はVisual Studio Codeにも同時に反映されます。

この拡張機能は、コンテキストに応じた補完機能、``x:DataType`` に対応した詳細なクイック情報表示、XAMLの「定義へ移動」機能、名前空間の自動インポート、イベントハンドラーの生成、実行可能な診断機能、適切な DPI 処理を備えた信頼性の高い組み込み XAML プレビューアなど豊富な機能を提供します。

**Avalonia for Visual Studio Code のインストール方法**
1. Visual Studio Codeで拡張機能ビューを開く
2. 検索バーに「Avalonia」と入力
3. 「Avalonia Team」によって公開されている「Avalonia for VSCode」を選択してインストール
4. 必要に応じてVisual Studio Codeを再読み込み

![IDE Setup](https://docs.avaloniaui.net/assets/images/download-vscode-avalonia-extension-e28be0f9bb959582e5c955ee54a2c358.png)

または、[Visual Studio Marketplaceから拡張機能をダウンロード](https://marketplace.visualstudio.com/items?itemName=AvaloniaTeam.vscode-avalonia)することもできます。  
XAMLプレビュー機能の使用方法について詳しくは、[XAML live preview](https://docs.avaloniaui.net/docs/app-development/xaml-preview-and-design-settings)のページを参照してください。
{{< /tab >}}

{{< tab name="Rider" >}}
macOS または Linux を使用している場合は、JetBrains Rider が推奨されます。  
Rider はこれらのオペレーティングシステム上でXAMLの組み込みサポートを含む、完全で統合された開発環境を提供します。  
作業中のXAMLをリアルタイムでプレビューできるようにするため、サードパーティ製プラグイン [AvaloniaRider](https://plugins.jetbrains.com/plugin/14839-avaloniarider) のインストールを検討してください。

**AvaloniaRider のインストール方法**
1. JetBrains Riderで Settings（設定）→ Plugins（プラグイン） を開く
2. Marketplace タブに移動
3. 検索バーに「AvaloniaRider」と入力
4. Install（インストール） をクリック
5. 追加のインストール手順に従う。   
インストールを完了するために、JetBrains Riderを再起動する必要がある場合があります。
![IDE Setup](https://docs.avaloniaui.net/assets/images/download-rider-avaloniarider-f7cbf3952120015b160d1b0fdd8d3b5c.png)

XAMLプレビュー機能の使用方法について詳しくは、[XAML live preview](https://docs.avaloniaui.net/docs/app-development/xaml-preview-and-design-settings)のページを参照してください。
{{< /tab >}}

{{< /tabs >}}