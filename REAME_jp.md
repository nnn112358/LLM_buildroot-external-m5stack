# AX630C Buildroot 外部ツリー

uboot、linux-kernel、mspを含む
このリポジトリは、[M5Stack](https://m5stack.com/)の[AX630C](https://docs.m5stack.com/en/module/Module-LLM)プラットフォームをサポートするためのBuildroot `BR2_EXTERNAL`ツリーです。BuildrootにはAX630Cのサポートが含まれているため、このプロジェクトは必須ではありませんが、このBR2_EXTERNALツリーはAX630Cプラットフォームの様々な機能を活用する方法を示すサンプル設定を提供しています。

## 利用可能な設定

このBR2_EXTERNALツリーは、以下の2つのBuildroot設定例を提供しています：

1. `m5stack_module_llm_4_19_defconfig`: AX630C LLM Discovery Kitボード向けの最小構成です。U-Bootブートローダー、Linuxカーネル、およびBusyboxのみで構成された最小限のユーザースペースをビルドします。

2. `m5stack_ax630c_lite_4_19_defconfig`: AX630C Kit Discovery Kitボード向けの最小構成です。U-Bootブートローダー、Linuxカーネル、およびBusyboxのみで構成された最小限のユーザースペースをビルドします。

なお、アップストリームのBuildrootにもAX630Cプラットフォーム用の事前定義された設定が含まれていますが、それらはU-BootとLinuxのアップストリームバージョンを使用しています。一方、このBR2_EXTERNALツリーの設定は、M5STACKが提供・サポートするバージョンを使用します。

## スターターパッケージ

ソースからすべてをビルドせずにAX630CプラットフォームでBuildrootを使用したい場合、以下のスターターパッケージを提供しています。各リリースとBuildroot設定ごとに、以下を提供します：

* スターターパッケージのビルド方法を説明するREADMEファイル
* SDカードにフラッシュ可能な事前ビルド済みイメージ（フラッシュ処理を最適化するためのブロックマップ付き）
* ターゲット向けアプリケーションをビルドするためのクロスコンパイラとライブラリを含むソフトウェア開発キット（SDK）
* ライセンスコンプライアンスのための、すべてのソフトウェアコンポーネントのオープンソースライセンスと完全なソースコード

## ソースからのBuildrotのビルド

### 前提条件

Buildrootを使用するには、ワークステーションにLinuxディストリビューションがインストールされている必要があります。最新の主要なLinuxディストリビューション（Ubuntu、Debian、Fedora、Redhat、OpenSuseなど）であれば問題ありません。

必要なパッケージは、[Buildrootマニュアルのシステム要件セクション](https://buildroot.org/downloads/manual/manual.html#requirement)に記載されています。

Debian/Ubuntuディストリビューションの場合、以下のコマンドで必要なパッケージをインストールできます：

```bash
$ sudo apt install debianutils sed make binutils build-essential gcc g++ bash patch gzip bzip2 perl tar cpio unzip rsync file bc git
```

### コードの取得

このBR2_EXTERNALツリーはBuildrootの`2023.02.x` LTSバージョンで動作するように設計されています。ただし、アップストリームのBuildrootに対していくつかの変更が必要なため、このBR2_EXTERNALツリーと一緒に独自のBuildrotフォークを使用する必要があります。具体的には`st/2023.02.10`ブランチを使用します。

### システムの設定とビルド

詳細な手順が説明されており、最終的にLLMに書き込む方法まで記載されています。サポートが必要な場合は、dianjixz@m5stack.comまでお問い合わせください。
