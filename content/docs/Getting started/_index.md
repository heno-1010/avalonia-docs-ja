---
weight: 3
---
# 始める
Avalonia（クロスプラットフォーム対応の .NET UI フレームワーク）を始めましょう。SDK をインストールし、IDE をセットアップして、最初のプロジェクトを作成します。

このセクションでは、Avalonia アプリケーションを一から作成し、実行できるようになるまでに必要な内容を解説します。ガイドは順番に進めることも、必要なものだけを参照することもできます。
{{< cards >}}

{{< card
    link="/docs/getting-started/install-avalonia/"
    title="Avaloniaをインストール"
    subtitle=".NET SDK と Avalonia のプロジェクトテンプレートをインストールします。"
>}}

{{< card
    link="/docs/getting-started/set-up-your-ide/"
    title="IDEをセットアップ"
    subtitle="JetBrains Rider、Visual StudioまたはVS CodeをAvalonia開発用に設定します。"
>}}

{{< card
    link="/docs/getting-started/create-your-first-project/"
    title="最初のプロジェクトを作成"
    subtitle="テンプレートを使ってAvaloniaアプリを作成し、実行します。"
>}}

{{< card
    link="/docs/getting-started/starter-tutorial/"
    title="スターターチュートリアル"
    subtitle="温度変換アプリを作成し、Avaloniaの基本的な概念を学びます。"
>}}

{{< /cards >}}

## Avaloniaとは？
Avaloniaは、.NET向けのオープンソースのクロスプラットフォームUIフレームワークです。独自のレンダリングエンジンを使用してコントロールを描画するため、どのプラットフォームでも同じ見た目と動作を実現できます。C#またはF#とXAMLで一度UIを作成すれば、Windows、macOS、Linux、iOS、Android、そしてWebAssemblyにデプロイできます。

WPFやUWPの経験がある場合、AvaloniaのXAMLやAPIは馴染みやすく感じるでしょう。XAMLベースのフレームワークが初めての場合は、スターターチュートリアルから始めることをおすすめします。

## 既に.NETとIDEをお持ちの場合
既に.NET 8以上とIDEの設定が完了している場合は、そのままプロジェクトの作成に進んで構いません。
```
dotnet new install Avalonia.Templates
dotnet new avalonia.mvvm -o MyApp
cd MyApp
dotnet run
```

## WPFからの移行ですか？
AvaloniaのAPIは意図的にWPFに近い設計になっていますが、スタイリング、テンプレート、プロパティシステムには重要な違いがあります。セクションごとの比較については、[WPF移行ガイド](/docs/)を参照してください。

既存のWPFアプリケーションをクロスプラットフォームで、書き直さずに動かしたい場合は、[Avalonia XPF](https://docs.avaloniaui.net/xpf)を使用することで、Avaloniaのレンダリングエンジン上でバイナリ互換のWPFサポートを利用できます。