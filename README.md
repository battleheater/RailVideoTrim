# RailVideoTrim

**Language / 言語**

[🇬🇧 English](#english) | [🇯🇵 日本語](#japanese)

## Japanese

## 大量の動画を、1本ずつ確認する必要はありません。

鉄道撮影では、列車が来るまで長時間カメラを回し続けることがあります。

問題は、撮影後です。

**「この大量の動画の、どこに列車が映っているのか？」**

これを1本ずつ再生して確認し、必要な部分を探してカットするのは、とても面倒で時間がかかる作業です。

さらに、不要な録画部分をそのまま保存しておけば、**高価なストレージ容量もどんどん消費していきます。**

RailVideoTrimは、これらの作業を自動化します。

### 複数の動画をまとめて放り込んで、ボタンを押すだけ。

どの動画をカットすべきか、自分で選ぶ必要さえありません。

長い動画も短い動画も関係なく、RailVideoTrimが動画を自動解析し、

* カットする価値がある尺が長い動画のみを処理対象として自動選別
* 列車などによる映像の変化を検出
* 被写体が映っていると思われる区間を自動判定
* 必要な区間だけを無劣化で出力
* 大量の動画をまとめて一括処理

します。

つまり、

> **「1本の長い動画を短くする」ためのツールではありません。**

> **「大量の動画を、自分で1本ずつ確認する作業をなくす」ためのツールです。**

そして、不要な録画時間を削除することで、**大切な動画を必要な部分だけ残し、ストレージ容量の節約にもつなげられます。**

撮影した動画をまとめてフォルダに入れたら、あとはRailVideoTrimに任せてください。

---

## AIは使用していません

RailVideoTrimは、AIによる画像認識やクラウドAIサービスを使用していません。

独自の画像解析と判定ロジックによって、動画内の映像変化を解析し、必要な区間を検出します。

そのため、

* AIへの動画アップロードが不要
* AIによる学習や情報漏洩を心配する必要がない
* インターネット接続がなくても使用できる
* 撮影した動画を外部サービスに送信しない

という特徴があります。

## 完全オフラインで動作

RailVideoTrimの動画解析は、**お使いのPC上だけで完結します。**

インターネットに接続して動画を解析する必要はありません。

撮影した大切な鉄道動画を、外部サーバーへアップロードすることなく、自分のPCだけで処理できます。

---

## RailVideoTrimが目指すもの

RailVideoTrimが減らしたいのは、動画の長さだけではありません。

**撮影後に大量の動画を1本ずつ確認する「時間」と「手間」。**

そして、**必要のない録画部分を保存し続けることで消費される「ストレージ容量」**です。

撮影した動画をまとめて投入して、あとは処理が終わるのを待つ。

**手作業による確認時間を減らし、必要な映像だけを残して、ストレージも効率よく使う。**

それがRailVideoTrimの目的です。


## 主な特徴

* **FFmpegの `-c copy` による無劣化カット**
* 原本のファイルは一切変更しません
* 被写体を検出した区間の前後に任意の余白を追加して保存可能
* 複数の動画をまとめて処理可能
* 1本の動画に複数回被写体が検出された場合は、最も被写体スコアが高い部分だけを自動選択して出力（全ての検出部分を出力することも可能）
* MP4 / MTS /MOVなど多くのフォーマットに対応
* ビデオ・音声以外のトラックも、可能な限り保持
* 音声形式などの互換性に応じてMP4 / MOVを使い分け


## 動作環境

### 対応OS

* Windows 10
* Windows 11

### 必要なソフトウェア

* FFmpeg

FFmpegがインストールされている場合は、その実行ファイルを自動的に検索して使用します。  
FFmpegがない場合は、「FFmpegを自動インストール」のボタンを押下すると、自動インストールが可能です。  
自動インストールにはWinGetコマンドを使用しますので、Wingetコマンドもない場合はWinGetをインストールしてください。  
または、ご自分で個別にFFmpegをダウンロードしてインストールすることも可能です。

## 基本的な使い方

### 1. 入力動画を選択

処理したい動画ファイル、または動画が入っているフォルダを指定、またはドラッグ＆ドロップします。
複数の動画をまとめて選択することもできます。

### 2. 出力先を指定

出力ファイルの保存先フォルダを指定します。
保存先が空欄の場合、自動的に入力動画と同じフォルダに「trim」というサブフォルダを作ってそこに保存します。

### 3. パラメータを設定

必要に応じて解析条件を変更します。

「前後余白」は、被写体が映っていると判断した区間の前後に、指定した秒数の余白が追加されます。

20-30秒前後が自然かと思いますが、お好みに応じて変更してください。

また「前後余白」の2倍より短い動画は、必然的にカットする部分がないので処理しません。

別途「これより短い動画は処理しない」という設定もあります。  
すなわち、「前後余白」の2倍、または「これより短い動画は処理しない」、どちらかより短い動画は処理しません。

その他のパラメーターは変更すると全く出力結果が変わってしまいますので、**基本的にデフォルト設定のまま使用することをお勧めします。**
パラメーターの意味は入力欄にマウスポインタを乗せると表示されますので、興味がある方は参考にしてください。

### 4. 解析・切り出し

解析を開始すると、動画のフレーム間の変化を調べ、必要な区間を自動的に検出します。

検出された区間には、設定した前後の余白を追加して切り出します。

## 出力ファイル

1本の動画から複数の区間が検出された場合、デフォルトでは最も画面の変化が大きい区間を被写体が映っている区間と判定し、その区間だけを出力します。

ただし、「複数区間を全て出力」のチェックボックスをONにした場合は、全ての区間を個別のファイルに出力します。

例：

```text
元動画
  ↓
20260830_123456.mp4

検出結果
  ↓
20260830_123456_001.mp4
20260830_123456_002.mp4
20260830_123456_003.mp4
```

動画の映像・音声は基本的に再エンコードせず、そのまま切り出します。

そのため、通常の動画変換と比較して**画質の劣化がありません**。


## ご注意

* 夜間など低照度・低コントラストな動画
* 俯瞰撮影など被写体が小さい動画
・カメラブレが激しい動画
* 木々の揺れなど、映像全体に継続的な変化がある

といった状況では、被写体が検出されなかったり、逆に何も映っていない区間が出力される場合があります。

作者の体感では、うまくカットできる動画は7割程度ですが、それでも自動で大幅にストレージを節約できるのは価値があると思います。

また、**列車を確実に検出できることを保証するものではありません。**
正常に出力されたことを確認してから、原本のファイルを削除することを強くおすすめします。

## FFmpegについて

RailVideoTrimは動画の解析・切り出しにFFmpegを使用します。

FFmpegそのものはRailVideoTrimに同梱していません。

FFmpegについては、以下の公式サイトを参照してください。

https://ffmpeg.org/

## ライセンス

RailVideoTrimのライセンスについては、同梱されている `LICENSE` ファイルを参照してください。

## フィードバック・不具合報告

不具合や改善要望がありましたら、下記の情報を添えてお知らせ下さい。

* RailVideoTrimのバージョン
* ウインドウ下部のログ欄に表示されている内容

- [X](https://x.com/battleheater_te)
- [Github Issues](https://github.com/battleheater/RailVideoTrim/issues)

## 応援について

RailVideoTrimを気に入っていただけましたら、開発を応援していただけると嬉しいです。

継続的な開発・改善の励みになります。

- [OFUSE](https://ofuse.me/battleheater)
- [Ko-fi](https://ko-fi.com/battleheater)
- [GitHub Sponsors](https://github.com/sponsors/battleheater)

---

**RailVideoTrim**
鉄道動画の「待ち時間」を、自動でカット。


## English

## You don’t have to review a large number of videos one by one.

When filming trains, you often have to keep the camera rolling for long periods until a train arrives.

The problem comes after you’ve finished filming.

**“Where in all these videos does the train actually appear?”**

Playing back each video one by one to find and cut out the necessary parts is a very tedious and time-consuming task.

Furthermore, if you keep saving the unnecessary footage, **it will rapidly consume your expensive storage space.**

RailVideoTrim automates these tasks.

### Just dump multiple videos in at once and press a button.

You don't even have to decide which videos to trim.

Whether the videos are long or short, RailVideoTrim automatically analyzes them and

* automatically selects only the long videos worth trimming for processing
* Detects changes in the footage caused by trains and other subjects
* Automatically identifies sections where the subject is likely to appear
* Outputs only the necessary segments without any loss of quality
* Batch-processes large numbers of videos at once

In other words,

> **This is not a tool for “shortening a single long video.”**

> **It is a tool designed to “eliminate the need to manually review large numbers of videos one by one.”**

Furthermore, by deleting unnecessary recording time, **you can keep only the essential parts of your important videos, which also helps save storage space.**

Simply place your recorded videos into a folder, and let RailVideoTrim handle the rest.

---

## No AI is used

RailVideoTrim does not use AI-based image recognition or cloud AI services.

Using its proprietary image analysis and decision-making logic, it analyzes changes in the video footage to detect the necessary segments.

As a result,

* No need to upload videos to AI
* No need to worry about AI training or data leaks
* Can be used without an internet connection
* Recorded videos are not sent to external services

These are its key features.

## Operates Completely Offline

RailVideoTrim’s video analysis is **completed entirely on your PC.**

There is no need to connect to the internet to analyze videos.

You can process your precious railway videos on your own PC without uploading them to external servers.

---

## What RailVideoTrim Aims to Achieve

RailVideoTrim aims to reduce more than just video length.

**It also aims to reduce the “time” and “effort” spent reviewing large volumes of footage one video at a time after filming.**

And it aims to reduce the **“storage space” consumed by continuing to save unnecessary portions of your recordings.**

Simply import all your recorded videos at once and wait for processing to finish.

**Reduce the time spent on manual review, keep only the footage you need, and use your storage space efficiently.**

That is the purpose of RailVideoTrim.


## Key Features

* **Lossless trimming using FFmpeg’s `-c copy` option**
* Does not modify the original files in any way
* Allows you to add custom margins before and after detected subject segments when saving
* Can process multiple videos at once
* If a subject is detected multiple times in a single video, only the segment with the highest subject score is automatically selected and output (it is also possible to output all detected segments).
* Supports many formats, including MP4, MTS, and MOV
* Preserves tracks other than video and audio whenever possible
* Selects between MP4 and MOV based on compatibility with audio formats and other factors


## System Requirements

### Supported Operating Systems

* Windows 10
* Windows 11

### Required Software

* FFmpeg

If FFmpeg is already installed, the program will automatically locate and use its executable file.
If FFmpeg is not installed, you can install it automatically by clicking the “Automatically Install FFmpeg” button.
The automatic installation uses the WinGet command, so if you do not have WinGet, please install it.
Alternatively, you can download and install FFmpeg manually.

## Basic Usage

### 1. Select Input Video

Specify the video file or folder containing the videos you want to process, or use drag-and-drop.
You can also select multiple videos at once.

### 2. Specify Output Location

Specify the folder where the output files will be saved.
If the output location is left blank, a subfolder named “trim” will be automatically created in the same folder as the input video, and the files will be saved there.

### 3. Set Parameters

Adjust the analysis settings as needed.

“Pre- and Post-Margins” adds a specified number of seconds of margin before and after the segments where the subject is detected.
A margin of around 20–30 seconds is generally considered natural.
Additionally, videos shorter than twice the “Pre- and Post-Margins” setting will not be processed, as there are no sections to trim.

There is also a separate setting that states, “Do not process videos shorter than this.”
In other words, videos shorter than twice the “Pre- and Post-Margin” value, or shorter than the value specified in “Do not process videos shorter than this,” will not be processed.

Changing other parameters will completely alter the output results, so **we generally recommend using the default settings.**
The meanings of the parameters are displayed when you hover your mouse pointer over the input fields, so please refer to them if you’re interested.

### 4. Analysis and Extraction

When analysis begins, the tool examines changes between video frames and automatically detects the necessary segments.

The detected segments are extracted with the specified before and after margins added.

## Output Files

If multiple segments are detected in a single video, by default, the system identifies the segment with the most significant change in the scene as the one containing the subject and outputs only that segment.

However, if you check the “Output all segments” checkbox, all segments will be output as separate files.

Example:

```text
Original Video
  ↓
20260830_123456.mp4

Detection Results
  ↓
20260830_123456_001.mp4
20260830_123456_002.mp4
20260830_123456_003.mp4
```

The video and audio are generally not re-encoded; they are extracted as-is.

Therefore, compared to standard video conversion, **there is no loss in image quality**.


## Precautions

* Videos shot at night or in other low-light, low-contrast conditions
* Videos where the subject is small, such as those shot from a bird’s-eye view
・Videos with severe camera shake
* Videos with continuous movement across the entire frame, such as swaying trees

In such situations, the subject may not be detected, or conversely, sections with no subject may be included in the output.

Based on the author’s experience, the tool successfully trims about 70% of videos, but even so, the ability to automatically save a significant amount of storage space is still valuable.

Additionally, **we do not guarantee that trains will be detected reliably.**
We strongly recommend that you verify that the output is correct before deleting the original file.

## About FFmpeg

RailVideoTrim uses FFmpeg for video analysis and trimming.

FFmpeg itself is not included with RailVideoTrim.

For more information about FFmpeg, please visit the official site below:

https://ffmpeg.org/

## License

For information on the RailVideoTrim license, please refer to the included `LICENSE` file.

## Feedback and Bug Reports
If you encounter any bugs or have any suggestions for improvements, please let us know by including the following information:

* RailVideoTrim version
* The content displayed in the log section at the bottom of the window

- [X](https://x.com/battleheater_te)
- [Github Issues](https://github.com/battleheater/RailVideoTrim/issues)

## Support

If you like RailVideoTrim, we’d appreciate your support for its development.

Your support encourages us to continue developing and improving the project.

- [OFUSE](https://ofuse.me/battleheater)
- [Ko-fi](https://ko-fi.com/battleheater)
- [GitHub Sponsors](https://github.com/sponsors/battleheater)

---

**RailVideoTrim**
Automatically trims the “waiting time” from train videos.
