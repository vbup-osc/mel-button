# 梅露按钮 / Mel Button

### https://yozoramel.org

相关链接 / Related Links:

* [Yozora Mel's Youtube channel](https://www.youtube.com/channel/UCD8HOxPs4Xvsm8H0ZxXGiBw)

* [Yozora Mel's Twitter](https://twitter.com/yozoramel)

## 参与完善本项目

欢迎参与完善这个并不成熟的项目，或者为我们提出宝贵的意见！

联系方式：Email: `support@vbup.org`

如有意完善此项目，请 Fork 本项目进行修改，完成修改后在本项目中发起一个 Pull Request。

### 添加或修改音频

**简述**：所有的音频信息都存储在 [assets/voices.json](https://github.com/voosc/mel-button/tree/master/assets/voices.json) 中，要添加或修改音频，你需要同时修改对应的文件。

音频一律为mp3格式，存储在 [static/voices](https://github.com/voosc/mel-button/tree/master/static/voices) 中。对应的URL为 `voices/`。

添加的新音频请先使用类似 Adobe Audition 的软件进行响度匹配，目前使用的标准为 ITU-R BS.1770-3，目标响度 -24LUFS，容差 2LU，最高实际峰值电平 -2dBTP。

如果需要对现有音频进行修改，建议将原音频文件删除，重新命名一个新文件，这样可以避免浏览器缓存问题。

修改音频之后请删除原音频文件。

**推荐使用 [voices.json 编辑工具](https://editor.vbup.org) 进行编辑。**

### 参与翻译

主程序翻译在 [assets/locales](https://github.com/voosc/mel-button/tree/master/assets/locales) 中的三个以语言名命名的 js 文件中。

语音的翻译在 [assets/voices.json](https://github.com/voosc/mel-button/tree/master/assets/voices.json) 中。

## 部署本地开发环境

本项目是使用 Vue + NuxtJS + Vuetify 开发的。

要部署本地开发环境，请首先安装最新版本的 Node 和 Yarn 包管理器。然后，请按照下列步骤操作：

1.Fork 并 Clone 代码到本地。

2.进入代码所在目录，运行 `yarn` 安装依赖。

3.运行 `yarn dev`，启动本地开发服务器，项目将被临时部署在 `localhost:3000` 上。在代码修改过程中，本地开发服务器可以即时更新修改结果。

4.要编译可用于部署的文件，请运行 `yarn generate`，这将在 `dist` 目录生成完全静态的文件。编译完成后，您可以直接将整个 `dist` 目录部署至 Github Pages 等静态文件托管服务上。

## LICENSE

本项目由 [VBUP（VOOSC)](https://space.bilibili.com/345725508) 制作。

程序部分: MIT

音频部分: [hololive 二次创作条款](https://www.hololive.tv/terms)

本项目为爱好者作品，与 hololive 官方没有关联。

## 特别感谢

#### 音频资源由夜空梅露的樱桃汁工厂提供。

[他们的 Bilibili 频道](https://space.bilibili.com/490670563/)

#### 本项目由 [Vercel](https://vercel.com/) 强力驱动。

[![Vercel Logo](https://cdn.jsdelivr.net/gh/paizi/vue-test/vercel.svg)](https://vercel.com)

以及所有支持这个项目的朋友，你们的鼓励是我们孜孜不倦的源动力，谢谢你们。

[![GitHub Contributors](https://contributors-img.web.app/image?repo=voosc/mel-button)](https://github.com/voosc/mel-button/graphs/contributors)

虚位以待...
