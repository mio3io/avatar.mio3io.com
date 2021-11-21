# アバター導入手順 Quest版

はじめてアバターを導入する方は、先に [UnityとVRCSDKの導入手順](vrcsdk.md) をご覧ください。

説明では薄荷を使用していますが、当モデルのアバターの導入方法はすべて一緒のためご自分のアバターに置き換えてご覧ください。

手順は次のとおりです。

1. [プロジェクトを作成](setup_quest.md?id=プロジェクトを作成)
2. [アバターの Unitypackage をインポート](setup_quest.md?id=アバターモデルをインポート)
3. [アバターフォルダ直下にあるプレハブを適当なシーンにドラッグ＆ドロップ](setup_quest.md?id=シーン上にプレハブを読み込む)
4. [VRCSDKを開きアップロード](setup_quest.md?id=アバターをアップロード)

次で各項目を詳しく説明します。

!> Unity は必ず**指定されたバージョン**をご利用ください。
現在のバージョンは[こちらから確認できます](https://docs.vrchat.com/docs/current-unity-version)。
VRCSDK は公式が配布している[最新のバージョン](https://vrchat.com/home/download)をご利用ください。

## プロジェクトを作成

Unity プロジェクトを作成し VRCSDK をインポートします。

## アバターモデルをインポート

BOOTH の購入ページから「`HakkaQuest_v1.2_(DateTime).zip`」というファイルをダウンロードして適当な場所に解凍します。

解凍したフォルダの直下にある `unitypackage` 拡張子のファイルをプロジェクトの「**Assets**」ウィンドウにドラッグ＆ドロップするか、メニューの`Assets > Import Package > Custom Package` からファイルを選択してインポートします。

![](images/setup/quest01.png ':class=ss')

## シーン上にプレハブを読み込む

インポートすると Project ウィンドウに `mio3io > HakkaQuest` というフォルダが作成されます。
`HakkaQuest` フォルダの直下にあるプレハブ `HakkaQuest.prefab` を適当なシーンの Hierarchy にドラッグ＆ドロップします

![](images/setup/quest02.png ':class=ss')

## アバターをアップロード

VRCSDK の Builder タブを開き ① にある「Active Build Target」が「**Android**」になっているかを確認してください。

「Android」になっていない場合は「**Switch Build Target to Android**」ボタンをクリックして切り替えます。

![](images/setup/quest03.png ':class=ss :size=450')

このとき「Switch Build Target to Android」が利用できない場合は次の手順で Android 用のモジュールを追加してください。

![](images/setup/quest04.png ':class=ss :size=800')

![](images/setup/quest05.png ':class=ss :size=800')

「`Build & Publish for Windows`」ボタンをおします。

少し待つと自動的に再生ボタンが押され Game タブにアップロード画面が表示されます。

任意の名前を入れアップロードします。

![](images/setup/pc04.png ':class=ss')

!> `Sharing` は必ず `Private` （アップロードした者だけ使用できる） のままにしてください。

新規でアップロードしたアバターは反映まで時間がかかるようなので、10分ほど待ってから確認してみてください。
ゲーム画面で読み込まれなくても Web サイトで確認できればアップロードされています。

## PC/Questに両対応する場合

すでに PC 版をアップロードしている場合は VRCSDK の Content Manager タブを開き、Quest 版を追加したいアバターの「Copy ID」で  Blueprint ID を取得します。Quest 版としてアップロードしたいアバターを選択した状態で Inspector ウィンドウに表示される「Blueprint ID」の部分に取得しておいた  Blueprint ID をペーストして Attach してからアップロードしてください。

先に Quest 版をアップロードしている場合は逆の手順で Blueprint ID を同じものにしてアップロードしてください。
