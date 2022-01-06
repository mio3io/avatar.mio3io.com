# アバター導入手順 PC 版

はじめてアバターを導入する方は、先に [Unity と VRCSDK の導入手順](vrcsdk.md) をご覧ください。

説明では薄荷を使用していますが、当モデルのアバターの導入方法はすべて一緒のためご自分のアバターに置き換えてご覧ください。

手順は次のとおりです。

1. [プロジェクトを作成](setup_pc.md?id=プロジェクトを作成)
2. [シェーダーと DynamicBone をインポート](setup_pc.md?id=前提アセットをインポート)
3. [アバターの Unitypackage をインポート](setup_pc.md?id=アバターモデルをインポート)
4. [プレハブを適当なシーンにドラッグ＆ドロップ](setup_pc.md?id=シーン上にプレハブを読み込む)
5. [VRCSDK を開きアップロード](setup_pc.md?id=アバターをアップロード)

次で各項目を詳しく説明します。

!> Unity は必ず**指定されたバージョン**をご利用ください。
現在のバージョンは[こちらから確認できます](https://docs.vrchat.com/docs/current-unity-version)。
VRCSDK は公式が配布している[最新のバージョン](https://vrchat.com/home/download)をご利用ください。

## プロジェクトを作成

Unity プロジェクトを作成し VRCSDK をインポートします。

## 前提アセットをインポート

シェーダーや Dynamic Bone など、アバター以外の必要なアセットのパッケージをインポートします。

薄荷の場合シェーダーは「ユニティちゃんトゥーンシェーダー 2.0（以降 UTS2）」を使用しています。

🍒 [ユニティちゃんトゥーンシェーダー 2.0](https://unity-chan.com/download/releaseNote.php?id=UTS2_0)

また当モデルは Dynamic Bone（有料）が必要です。アセットストアで購入してください。

🍒 [Dynamic Bone](https://assetstore.unity.com/packages/tools/animation/dynamic-bone-16743)

Dynamic Bone など購入したアセットは `Window > Package Manager` の `My Assets` からインポートすることもできます。

!> 近い将来（おそらく 2022 年の早い時期）に DynamicBone の代替となるアセットを公式が提供する予定で、 DynamicBone は不要になるそうです。

![](images/setup/pc_dynamicbone.png ":class=ss")

Dynamic Bone がインポートされていない場合 Missing エラーでアップロードできません。所持していない場合は Dynamic Bone が設定されているコンポーネントをすべて削除する必要があります。

🌱 [Missing Remover](https://riku1227.booth.pm/items/1969758) - Missing エラーを削除してくれるツール

> 使用シェーダーは各アバター販売ページに書いていますが、当モデルは基本的に「[UTS2](https://unity-chan.com/download/releaseNote.php?id=UTS2_0)」または「[lilToon](https://booth.pm/ja/items/3087170)」を使用しています。アクセサリーなどで [UnlitWF](https://github.com/whiteflare/Unlit_WF_ShaderSuite/releases) や [メガネ向けガラスシェーダー](https://oyasumisan.booth.pm/items/1035152) を使用しています。モデルやバージョンによって異なるため、各アバター販売ページの「設定済みシェーダー」の項目をご確認ください。

## アバターモデルをインポート

BOOTH の購入ページから「`Hakka_v1.2_VRC_(DateTime).zip`」というファイルをダウンロードして適当な場所に解凍します。いくつかファイルがありますが、ZIP ファイル名に `_VRC` とついているものが VRChat 用のパッケージです。

解凍したフォルダの直下にある `unitypackage` 拡張子のファイルをプロジェクトの「**Assets**」ウィンドウにドラッグ＆ドロップするか、メニューの`Assets > Import Package > Custom Package` からファイルを選択してインポートします。

![](images/setup/pc01.png ":class=ss")

## シーン上にプレハブを読み込む

インポートすると Project ウィンドウに `mio3io > Hakka` というフォルダが作成されます。
`Hakka` フォルダの直下にあるプレハブ `Hakka_v.x_Normal.prefab` を適当なシーンの Hierarchy にドラッグ＆ドロップします

![](images/setup/pc02.png ":class=ss")

右下のバーでファイル一覧の表示形式を切り替えられます。

アバターがピンク色になっている場合は必要なシェーダーがインポートされていません。

![](images/setup/materialerror.png ":class=ss :size=220")

あとからシェーダーを追加しても表示がおかしくなる場合は一部のパラメータが消えてしまっている可能性があるため、一旦アバターのフォルダを削除してからシェーダー、アバターの順でインポートし直してください。

![](images/setup/materialerror2.png ":class=ss :size=323")

プレハブやモデルのサムネイルだけがマテリアルエラーになる場合は、ファイルを選択して右クリック > Reimport をしてみてください。

?> プレハブとはシーン上で組み立てたオブジェクトの情報を保存・使い回しできるようにした箱です。揺れものや VRC Avatar Descriptor などが設定された状態になっているため「まって、VRC Avatar Descriptor って何？」という方でも簡単にアバターを使用できます。
プレハブはリンクしており中身を編集すると同じプレハブオブジェクトすべてに反映されます。Unpack をすることでリンクが切れますが、アップデート内容などが適用されなくなる場合があります。

## アバターをアップロード

VRCSDK の Builder タブを開き「`Build & Publish for Windows`」ボタンをおします。

![](images/setup/pc03.png ":class=ss :size=500")

「`A Material on this avatar has custom shader keywords.`」というメッセージはエラーではありません。UTS2 で非推奨のカスタムキーワードを使用しているための警告なので、無視してそのままアップロードしてください。Auto Fix してしまうと表示がおかしくなる場合があります。もしアップロード出来ない場合は別の何かが原因なので「これを Auto Fix したらいけるのでは？」と思わないでください。

ただし `Streaming Mip Maps` というエラーは Auto Fix しても大丈夫です。

![](images/setup/pc_mipmaperror.png ":class=ss :size=500")

少し待つと自動的に再生ボタンが押され Game タブにアップロード画面が表示されます。

任意の名前を入れアップロードします。

![](images/setup/pc04.png ":class=ss")

!> `Sharing` は必ず `Private` （アップロードした者だけ使用できる） のままにしてください。

新規でアップロードしたアバターは反映まで時間がかかるようなので、10 分ほど待ってから確認してみてください。
ゲーム画面で読み込まれなくても Web サイトで確認できればアップロードされています。
