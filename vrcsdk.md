# UnityとVRCSDKの導入手順

すでにアバターをアップロードしたことのある方は、この章は飛ばしても問題ありません。

!> [VRChat](https://hello.vrchat.com/) のアカウントを登録してしばらく遊び、ユーザーのトラストレベルが「User」にならないとオリジナルのアバターはアップロードできません。また、アカウントは公式で登録するか Steam のアカウントを使用するか選べますが **VRChat公式アカウント** を使用しないとアップロードできないためご注意ください。

?> Unity とは VRChat を動かしているゲームエンジンです。アバターを使用するには Unity 上で組み立てて VRChat へアップロードします。そのため、Unity の操作方法などある程度の予備知識が必須になります。このドキュメントでは基本情報については説明していないため、[Unity マニュアル](https://docs.unity3d.com/ja/2019.4/Manual/UnityManual.html)などを併読してください。

?> VRCSDK とは VRChat用のアバターの作成キットです。「VRChat用」のため、Cluster など他のプラットホームにアバターを利用する際には使用しません。

## UnityHub のインストール

まずは次のページから UnityHub をダウンロードしてインストールします。

🍒 [Unity をダウンロード](https://unity3d.com/jp/get-unity/download)

![](images/vrcsdk/unityhub_download.png ':class=ss')

Unity 単体か UnityHub どっちでもいいのですが、UnityHub 前提で説明をすすめます。

?> UnityHub は複数のバージョンの Unity を一元管理するインストーラーです。ゲームによって使用する Unity のバージョンは異なりますが、VRChat が指定する Unity のバージョンも変更されることがあるため Hub を使用しておくとスムーズに対応できます。

## Unity のインストール

UnityHub の「インストール」タブの「エディターをインストール」から指定されたバージョンをインストールします。UnityHub もたまにアップデートされるため画面が異なる場合があります。

![](images/vrcsdk/unity01.png ':class=ss')

![](images/vrcsdk/unity02.png ':class=ss')


2021年11月現在のバージョンは「Unity 2019.4.31f1.」です。
最新のバージョンは[こちらのページ](https://docs.vrchat.com/docs/current-unity-version)で確認できます。

## プロジェクトの作成

「プロジェクト」タブを開き「新しいプロジェクト」をクリックします。

![](images/vrcsdk/unity03.png ':class=ss')

使用する Unity のバージョンを確認し、任意の名前をつけてプロジェクトを作成します。

![](images/vrcsdk/unity04.png ':class=ss')

プロジェクトのセットアップには数分かかることがあります。

!> ひとつのプロジェクトでいろいろなアバターを管理するよりも、アセットをインポートする手間はかかりますがある程度分けて作成することをおすすめします。できればアバターごとにプロジェクトを作成するとよいでしょう。
インポートしたアセットがプロジェクト内の他のアセットに予期せぬ影響を及ぼしたり最悪プロジェクト使用不能になることもあり、一度にすべてのアバターが電子の藻屑となってしまうためです。

## VRCSDK のインポート <!-- {docsify-ignore-all} -->

VRChat公式サイトの「[Downloadページ](https://vrchat.com/home/download)」から「Download SDK3 - Avatars」をダウンロードします。※ログインが必要です

🍒 [VRCSDK のダウンロード](https://vrchat.com/home/download)

![](images/vrcsdk/vrchat_download.png ':class=ss')

VRCSDK には「ワールド用」と「アバター用」の2つがあるため、間違えないように注意しましょう。

プロジェクトの「Assets」ウィンドウにダウンロードした unitypackage をドラッグ＆ドロップするか、メニューの `Assets > Import Package > Custom Package` からファイルを選択してインポートします。

![](images/vrcsdk/unity05.png ':class=ss')

パッケージの大きさによって数分かかることがあります。

VRCSDK のコントロールパネルを開きログインします。

![](images/vrcsdk/unity06.png ':class=ss')
