# RailVideoTrim v1.2.0

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

## 対応OS

* Windows 11

## 対応フォーマット

* MP4
* MOV
* mts
* 上記以外は未確認ですが、FFmpegが対応しているフォーマットであれば処理可能な可能性があります


## インストール方法

ダウンロードしたZIPファイルを解凍し、RailVideoTrim.exeをダブルクリックするだけで起動します。

## Windows SmartScreenについて

初回起動時に「WindowsによってPCが保護されました」
という警告が表示される場合があります。

これはRailVideoTrimが新しいアプリであり、
Microsoft Defender SmartScreenによる十分な評価が
まだ蓄積されていないためです。

公式サイトからダウンロードしたファイルであることを
確認したうえで、「詳細情報」→「実行」をクリックすると起動できます。

## 必要なソフトウェア

* FFmpeg

FFmpegがインストールされている場合は、その実行ファイルを自動的に検索して使用します。  
FFmpegがない場合は、「FFmpegを自動インストール」のボタンを押下すると、公式サイトからFFmpegのZIPファイルをダウンロードし、自動インストールが可能です。（この方法を推奨します）  
別途WinGetコマンドを使用して自動インストールすることも可能です。  
または、ご自分でFFmpegのフォルダを指定して使用するすることも可能です。

## 基本的な使い方

### 1. 入力動画を選択

処理したい動画ファイル、または動画が入っているフォルダを指定、またはドラッグ＆ドロップします。
複数の動画をまとめて選択することもできます。

フォルダを追加する場合は、「サブフォルダを含む」をONにすると、指定したフォルダ以下を再帰的に検索して、サブフォルダ内の対応動画ファイルも処理対象にできます。
OFFの場合は、指定したフォルダの直下にある対応動画ファイルだけが処理対象になります。

### 2. 出力先を指定

出力ファイルの保存先フォルダを指定します。
「入力ファイルと同じフォルダ内の\\trim」がONの場合は、各入力動画の親フォルダに「trim」フォルダを作成して、そこに保存します。サブフォルダを含めて検索した場合も、各動画の親フォルダが基準になります。
OFFの場合は、「出力フォルダ」で指定した1つのフォルダに保存します。

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
* 1カットに複数の列車が映っている動画
* カットの冒頭からすでに列車が映っている動画

といった状況では、適切にカットされない場合があります。

作者の体感では、うまくカットできる動画は8割程度ですが、それでも自動で大幅にストレージを節約できるのは価値があると思います。

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

- [Amazonギフト券](https://www.amazon.co.jp/dp/B004N3APGO?th=1)
- [OFUSE](https://ofuse.me/battleheater)
- [Ko-fi](https://ko-fi.com/battleheater)
- [GitHub Sponsors](https://github.com/sponsors/battleheater)

---

**RailVideoTrim**
鉄道動画の「待ち時間」を、自動でカット。


## English

## System Requirements

## Supported Operating Systems

* Windows 11

## How to Install

Simply unzip the downloaded ZIP file and double-click RailVideoTrim.exe to launch the program.

## Supported Formats

* MP4
* MOV
* mts
* Formats other than those listed above have not been verified, but they may be processable if they are supported by FFmpeg.

## About Windows SmartScreen

When you launch the program for the first time, you may see a warning that says
“Windows has protected your PC.”

This is because RailVideoTrim is a new app,
and Microsoft Defender SmartScreen has not yet accumulated
enough evaluation data for it.

After confirming that the file was downloaded from the official website,
click “More info” → “Run” to launch the program.

## Required Software

* FFmpeg

If FFmpeg is already installed, the program will automatically search for and use its executable file.
If FFmpeg is not installed, clicking the “Automatically Install FFmpeg” button will download the FFmpeg ZIP file from the official website and install it automatically. (This method is recommended.)
You can also use the WinGet command to perform an automatic installation.
Alternatively, you can specify the FFmpeg folder yourself.

## Basic Usage

### 1. Select Input Video

Specify the video file or folder containing the videos you want to process, or use drag-and-drop.
You can also select multiple videos at once.

### 2. Specify Output Location

Specify the folder where the output files will be saved.
When “Use a \\trim folder next to each input file” is enabled, a “trim” subfolder is automatically created in the parent folder of each input video, and the files are saved there. When subfolder search is enabled, each video's parent folder is used as the base independently.
When it is disabled, all output files are saved in the single folder specified in “Output folder”.

When adding a folder, enable “Include subfolders” to recursively search the specified folder and process supported video files found in its subfolders. When disabled, only supported video files directly inside the specified folder are processed.

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
* Videos with continuous movement throughout the footage, such as swaying trees
* Videos where multiple trains appear in a single shot
* Videos where a train is already visible at the beginning of a shot

In situations like these, the video may not be cut appropriately.

Based on the author’s experience, the system successfully cuts about 80% of videos, but even so, the ability to automatically save a significant amount of storage space is still valuable.


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

- [Amazon Gift Card](https://www.amazon.co.jp/dp/B004N3APGO?th=1)
- [OFUSE](https://ofuse.me/battleheater)
- [Ko-fi](https://ko-fi.com/battleheater)
- [GitHub Sponsors](https://github.com/sponsors/battleheater)

---

**RailVideoTrim**
Automatically trims the “waiting time” from train videos.
