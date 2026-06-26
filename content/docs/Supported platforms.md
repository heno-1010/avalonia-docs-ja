---
type: docs
weight: 2
---
# 対応プラットフォーム
Avaloniaアプリは、Windows, macOS, Linux, iOS, Android, WebAssemblyを作ることができます。  
サポートのレベルは、オペレーティングシステムのバージョンによって異なり、3つのティア（Tier）に分類されています。  
これらのティアは、Avaloniaのメジャーリリースごとに見直されるため、時間の経過と共にティアが移行する場合があります。

**Tier 1: 完全なテストとサポート**
{{< callout type="tip" title="Tier 1: 完全なテストとサポート" >}}
全てのリリースにおいてテストが実施されます。このプラットフォームで発生したバグは修正され、コミュニティからのプルリクエスト（PR）も積極的にレビューされ、マージされます。
{{< /callout >}}

**Tier 2: ベストエフォート**
{{< callout type="info" title="Tier 2: ベストエフォート" >}}
自動テストの対象（テストマトリクス）には含まれていませんが、ベストエフォート（最大限の努力）で動作が維持されます。Issueの優先順位はティア1の作業よりも低く設定されるため、一部の問題は修正されない可能性があります。コミュニティからのPRはケースバイケースで評価され、メンテナンスの負担が大きい場合は、商用サポートによる支援が必要になる場合があります。
{{< /callout >}}

**Tier 3: 商用サポートのみ**
{{< callout type="warning" title="Tier 3: 商用サポートのみ" >}}
Tier 1、Tier 2に含まれていないすべてのプラットフォームが対象です。Issueはクローズされ、PRのレビューは行われません。このプラットフォームでAvaloniaを使用する必要がある場合は、「Enhanced Support」を参照してください。
{{< /callout >}}

## Windows
Avaloniaは、Windows上でWin32 APIを直接使用します。.NET SDK以外に、追加のワークロードや依存関係は必要ありません。
| バージョン | 最小ビルド | アーキテクチャ | ティア |
|---|---|---|---|
| Windows11 | 24H2 (build 26100) | x64, ARM64 | Tier 1 |
| Windows11 | 22H2 (build 22621) | x64, ARM64 | Tier 2 |
| Windows 10 | 22H2 (build 19045) | x64 | Tier 2 |
| Windows 10 / 11 | 以前のビルド | x64, x86 | Tier 3 |

WinFormsの相互運用（interop）やその他のWindows固有の機能については、「Windows platform guide」を参照してください。

## macOS
Avaloniaは、独自のネイティブObjective-C++ バックエンドを搭載しており、標準の .NET macOS ワークロードは使用しません。そのため、Windows や Linux から macOS アプリをクロスコンパイルすることができます。
| バージョン | 名前 | アーキテクチャ | ティア |
|---|---|---|---|
| macOS 26 | Tahoe | ARM64 (Apple Silicon), x64 | Tier 1 |
| macOS 15 | Sequoia | ARM64, x64 | Tier 2 |
| macOS 14 | Sonoma | ARM64, x64 | Tier 2 |
| macOS 13以前 |  |  | Tier 3 |

ネイティブメニュー、プラットフォームの慣習、およびネイティブビューの埋め込みについては、「macOS platform guide」を参照してください。

## iOS and iPadOS
iOSにおける.NETのサポートは、MAUIのライフサイクルに従います。MicrosoftがMAUIのサポートポリシーに基づいてモバイルOSバージョンのサポートを終了した場合、Avaloniaにおけるそのバージョンへのサポートも同様に終了します。
| バージョン | アーキテクチャ | ティア |
|---|---|---|
| iOS / iPadOS 26 | ARM64 | Tier 1 |
| iOS 18.x | ARM64 | Tier 2 |
| iOS 17.x以前 | ARM64 | Tier 3 |

最小対応 .NET バージョン: .NET 10.0  
モバイル向けの .NET バージョンは、MAUI のサポートポリシーに従います。
Microsoft は .NET 10 SDK から .NET 8 のモバイルワークロードを削除したため、.NET 10 SDK を使用している場合は .NET 8 向けの iOS ビルドを作成できません。  
セットアップ手順については、「iOS platform guide」を参照してください。

## Android
Androidにおける.NETのサポートは、MAUIのライフサイクルに従います。MicrosoftがMAUIのサポートポリシーに基づいてモバイルOSバージョンのサポートを終了した場合、Avaloniaにおけるそのバージョンへのサポートも同様に終了します。
| バージョン | APIレベル | アーキテクチャ | ティア |
|---|---|---|---|
| Android 16 | API 36 | ARM64, x64 | Tier 1 |
| Android 12 to 15 | API 31 to 35 | ARM64, ARM32, x64 | Tier 2 |
| Android 11以前 | API 30以下 |  | Tier 3 |

最小対応 .NET バージョン: .NET 10.0  
モバイル向けの .NET バージョンは、MAUI のサポートポリシーに従います。
Microsoft は .NET 10 SDK から .NET 8 のモバイルワークロードを削除したため、.NET 10 SDK を使用している場合は .NET 8 向けの Android ビルドを作成できません。  
セットアップ手順については、「Android platform guide」を参照してください。

## Desktop Linux
Avaloniaは、Linux上でX11を直接ターゲットにしています。Waylandのサポートは現在プレイベートプレビュー段階です。.NET SDK をサポートし、X11 またはフレームバッファ機能を備えたほとんどのディストリビューションで Avalonia アプリケーションを実行できます。
| ディストリビューション | バージョン | アーキテクチャ | ティア |
|---|---|---|---|
| Ubuntu | 25.x | x64, ARM64 | Tier 1 |
| Fedora | 43 | x64 | Tier 1 |
| Debian | 13 (Trixie) | x64, ARM64 | Tier 1 |
| Ubuntu | 16.04 to 24.x | x64, ARM64 | Tier 2 |
| Fedora | 30 to 42 | x64 | Tier 2 |
| Debian | 9 (Stretch) to 12 | x64, ARM64 | Tier 2 |
| その他のディストリビューション | （Arch、Alpine、NixOS、Gentoo、その他） | 各種 | Tier 3 |

**レンダリング**：Skiaを介したOpenGL（X11）、またはソフトウェアレンダリング（フレームバッファ）  
**glibcの要件**：Skiaは glibc 2.17 をベースにビルドされています。muslなど、異なるCライブラリを使用しているディストリビューションでは、カスタムの libSkiaSharp.so をビルドする必要があります。詳細は「SkiaSharp」を参照してください。カスタムのSkiaビルドが必要なディストリビューションはティア 3となります。

**必要なパッケージ**
```
libx11-6 libice6 libsm6 libfontconfig1
```
WSL 2 およびその他の設定の詳細については、「Linux platform guide」を参照してください。

### Embedded Linux
Avaloniaは、組み込みLinuxデバイス上での実行をサポートしており、LinuxフレームバッファまたはDRM（Direct Rendering Manager）のいずれかを使用できます。
| ディストリビューション | アーキテクチャ | ランタイム識別子 | ティア |
|---|---|---|---|
| Raspberry Pi OS | ARM64, ARM32 | ``linux-arm64``, ``linux-arm`` | Tier 1 |
| その他の組み込み Linux | 各種 | 各種 | Tier 3 |

**必要パッケージ**：``libgbm1``,``libgl1-mesa-dri``,``libegl1-mesa``,``libinput10``  
ディスプレイ出力の設定やデバイスのセットアップについては、「Embedded Linux guide」を参照してください。

## WebAssembly
Avaloniaは、完全なWebAssemblyサポートを備えたあらゆるブラウザ上で動作します。サーバー側のコンポーネントは不要です。

| 要件 | 詳細 |
|---|---|
| .NET バージョン | .NET 8 以降 |
| ブラウザのサポート | WebAssemblyをサポートするすべてのブラウザ（Can I use WebAssembly） |
| レンダリング | CanvasKit（WebGL）を介したSkia |

セットアップとデプロイについては、「WebAssembly platform guide」を参照してください。

## プラットフォーム固有の修正への貢献
プラットフォーム固有の貢献（コントリビューション）は歓迎しますが、プロジェクトを健全に維持するため、上記のティア区分に沿ったものである必要があります。

**Tier 1** 修正は常に歓迎され、通常のレビュー手続きを経て取り込まれます。

**Tier 2** ケースごとに評価されます。レビューでは、実装の複雑さ、Tier 1 への回帰（リグレッション）リスク、そして継続的な保守コストが考慮されます。保守負担が大きい場合、その作業には商用契約が必要になることがあります。

**Tier 3** 修正は、レビューを行う前に商用契約が必要です。これは変更がどれほど小さく見えても同様です。なぜなら、コストはパッチそのものではなく、その変更をリリースごとに維持・テストし続けることにあるためです。

自分の貢献に商用契約が必要かどうか分からない場合は、作業を始める前に問い合わせてください。事前に確認することで、双方の時間を節約できます。