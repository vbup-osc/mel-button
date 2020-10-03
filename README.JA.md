# メルボタン / Mel Button

### https://yozoramel.org

関連URL / Related Links:

* [Yozora Mel's Youtube channel](https://www.youtube.com/channel/UCD8HOxPs4Xvsm8H0ZxXGiBw)

* [Yozora Mel's Twitter](https://twitter.com/yozoramel)

## プロジェクトのリファインに参加

この未熟なプロジェクトの改良に参加したり、あなたの意見をお聞かせください。

連絡先: Eメール： `support@vbup.org`

このプロジェクトを改善したい場合は、このプロジェクトをForkして変更を加え、変更後にこのプロジェクトでPull Requestを起動してください。

### オーディオの追加や変更

**簡潔な説明**：すべてのオーディオ情報は[assets/voices.json](https://github.com/voosc/mel-button/tree/master/assets/voices.json)に格納されています，オーディオを追加または修正するには、対応するファイルを同時に修正する必要があります。

音声は常にmp3形式で、[static/voices](https://github.com/voosc/mel-button/tree/master/static/voices)に保存されています。対応するURLは `voices/` です。

追加された新しいオーディオは、現在標準のITU-R BS.1770-3、ターゲットラウドネス-24LUFS、公差2LU、最大実際のピークレベル-2dBTPを使用して、Adobe Auditionに似たソフトウェアを使用して、最初にラウドネスを一致させる必要があります。

既存のオーディオを修正する必要がある場合は、ブラウザのキャッシュの問題を避けるために、元のオーディオファイルを削除し、新しいオーディオファイルの名前を変更することをお勧めします。

音声を修正した後は、元の音声ファイルを削除してください。

**編集には[voice.json編集ツール](https://editor.vbup.org)の利用をお勧めします。**

### 翻訳への参加

メインのプログラムは、[assets/locales](https://github.com/voosc/mel-button/tree/master/assets/locales)にある3つの言語名のjsファイルで翻訳されています。

音声の翻訳は[assets/voices.json](https://github.com/voosc/mel-button/tree/master/assets/voices.json)にあります。

## ローカル開発環境のデプロイ

このプロジェクトはVue + NuxtJS + Vuetifyを使って開発しています。

ローカル開発環境をデプロイするには、まず最新版のNodeとYarnパッケージマネージャをインストールします。 そして、以下の手順に従ってください。

1.コードをローカルにフォークしてクローンします。

2.コードのあるディレクトリに移動して `yarn` を実行し、依存関係をインストールします。

3.`yarn dev` を実行してローカル開発サーバを起動すると、プロジェクトが `localhost:3000` に一時的にデプロイされる。 ローカルの開発サーバーは、コードが修正されている間に変更を即座に更新できるようになります。

4.デプロイ用のファイルをコンパイルするには、`yarn generate`を実行すると、`dist`ディレクトリに完全に静的なファイルが生成されます。 コンパイルしたら、`dist` ディレクトリ全体を Github Pages のような静的ファイルホスティングサービスに直接デプロイすることができます。

## LICENSE

このプロジェクトは[VBUP(VOOSC)](https://space.bilibili.com/345725508)によるものです。

プログラムパート：MIT

音声パート：[ホロライブ二次的創作ライセンス規約](https://www.hololive.tv/terms)

この企画は趣味人の作品であり、ホロライブとは正式には提携していません。

## とくれい

#### 音声提供：夜空メルのアセロラジュース工場。

[彼らのビリビリチャンネル](https://space.bilibili.com/490670563/)

#### このプロジェクトは、[Vercel](https://vercel.com/)によって強く推進されています。

[![Vercel Logo](https://cdn.jsdelivr.net/gh/paizi/vue-test/vercel.svg)](https://vercel.com)

そして、このプロジェクトを支えてくださった皆様の励ましが、私たちのたゆまぬ努力の原動力となっています、ありがとうございました。

[![GitHub Contributors](https://contributors-img.web.app/image?repo=voosc/mel-button)](https://github.com/voosc/mel-button/graphs/contributors)

空席待ち...
