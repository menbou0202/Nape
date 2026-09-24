# 自作トラックボール「Nape」ビルドガイド

![](images/top.jpeg)

Napeはオープンソースの小型トラックボールデバイスです。PCBの製造や組み立て、使用にははんだ付けやコーディング、Gitなど専門知識がある程度必要になります。
気軽に使いたい方はKeychronから一般販売されているNapeの製品版「Nape Pro」の購入を強くお勧めします。

## 部品・工具の確認

まずは必要な部品・工具が揃っているか確認しましょう。

### 部品

以下の部品が必要です。

![](images/DSCF0448.jpeg)

![](images/DSCF0449.jpeg)


| No. | 部品 | 点数 | 主な購入先 |
|-----|------|------|------------|
| 1  | プリント基板（=PCB）             | 1    | — |
| 2  | PMW3610、レンズ                  | 1    | [AliExpress](https://ja.aliexpress.com/item/1005007118767775.html) |
| 3  | スイッチソケット（Choc）         | 3    | [AliExpress](https://ja.aliexpress.com/item/1005006007846154.html) / [遊舎工房](https://shop.yushakobo.jp/products/a01ps) |
| 4  | タクトスイッチ                   | 3    | [AliExpress](https://ja.aliexpress.com/item/1005001629184984.html) / [遊舎工房](https://shop.yushakobo.jp/products/a0800ts-01-1) |
| 5  | 水平スライドスイッチ             | 1    | [AliExpress](https://ja.aliexpress.com/item/32810428058.html) / [遊舎工房](https://shop.yushakobo.jp/products/5624) |
| 6  | M2ねじ 8mm                       | 4    | [Amazon（黒）](https://www.amazon.co.jp/dp/B0CQN8XRN1) / [Amazon（白）](https://www.amazon.co.jp/dp/B083DLYZBP) |
| 7  | セラミック支持球                 | 3    | [Amazon](https://www.amazon.co.jp/dp/B0CCJ2JQYD) |
| 8  | M2インサートナット               | 4    | [Amazon](https://www.amazon.co.jp/dp/B0CTTLJL6S) |
| 9  | 磁石（直径0.6×0.3cm）                             | 4    | [ダイソー](https://jp.daisonet.com/products/4549131156621) |
| 10 | トッププレート（3Dプリント品）   | 1    | — |
| 11 | ボトムプレート（3Dプリント品）   | 1    | — |
| 12 | ボールケース 25mm / 19mm（3Dプリント品）     | 1    | — |
| 13 | リセットボタン（3Dプリント品）   | 1    | — |
| 14 | スイッチキャップ（3Dプリント品） | 1    | — |
| 15 | キーキャップ（3Dプリント品）     | 3    | — |
| 16 | クッションゴム                   | 4    | [Amazon](https://www.amazon.co.jp/dp/B00V5MQQB4) |
| 17 | Seeed XIAO BLE nRF52840          | 1    | [秋月電子通商](https://akizukidenshi.com/catalog/g/g117341/) |
| 18 | キースイッチ（Lofree Low-profile POM） | 3    | [Lofree](https://lofree.co.jp/collections/switch) |
| 19 | トラックボール25mm / 19mm                     | 1    | [Amazon](https://www.amazon.co.jp/dp/B0D4DYH8XY), [Shakupan（Booth）](https://shakupan.booth.pm/items/6457643) |
| 20 | リチウムポリマーバッテリー（3.7V、PH2ピンコネクタ ※極性注意） | 1 | [Nape用バッテリーの選定・加工について](https://men-bou.net/nape-battery/) |

以下、各部品の注意事項を記載します。よく読んでからご購入ください。

#### トラックボールの互換性

![左：エレコム製、右：Shakupan製](images/NapeBuildGuide_00065.jpeg)

*左：エレコム製、右：Shakupan製*

以下は、Napeで動作確認済みのトラックボールです。表にない製品・カラーは、動作しない可能性があります。

| メーカー・製品 | サイズ |  動作確認済み|
|---|---:|---|
| [エレコム](https://www.amazon.co.jp/dp/B0D4DYH8XY) | 25mm |  レッド、シルバー|
| ペリックス | 25mm |  レッド（他の色は未確認）|
| [Shakupan（染色ボール）](https://shakupan.booth.pm/items/6457643) | 25mm | ブラック、ライトブルー、グレー（他の色は未確認） |
| Shakupan（フロストトラックボール） | 25mm | ブルー（他の色は未確認） |
| Keychron（Nape Pro向け） | 25mm | ブルー、シルバー（ホワイト、パープル、イエロー、オレンジは動作しません！） |

エレコム製やペリックす製、Keychron製は滑りも感度も良いのが特徴です。Shakupan製はエレコム製よりもややザラッとした操作感になるため、好みに応じて選択してください。[ポナンザ](https://www.amazon.co.jp/dp/B000AR70IS)などで定期的に磨くとスベスベ感を維持できます。

#### リチウムポリマーバッテリー

リチウムポリマーバッテリー（リポバッテリー）はスマホなどに搭載されているリチウムイオンバッテリーとは異なり、発火のリスクが高いバッテリーです。各自購入したバッテリーの注意事項をよく読み、適切に取り扱ってください。**取り扱いの不備により発生した事故などの責任は負いかねます。**  
就寝中や外出中など、バッテリーから目を離した状態でのUSB充電は避けてください。

設計者が動作を確認した市販バッテリーはこちらの記事にまとまっています。

[Nape用リポバッテリーの選定・加工についての備忘録](https://men-bou.net/nape-battery/)

### 必要な工具

以下の工具をご用意ください。

| 部品 | 購入先URL | 備考 |
|----|----|----|
| はんだごて | [https://www.amazon.co.jp/dp/B006MQD7M4](https://www.amazon.co.jp/dp/B006MQD7M4) | 温度調整できるもの。260℃〜320℃を使用します。 |
| こて台 | [https://www.amazon.co.jp/dp/B000TGNWCS](https://www.amazon.co.jp/dp/B000TGNWCS) | ←リンクはクリーニングワイヤーとセットのもの |
| はんだ | [https://www.amazon.co.jp/dp/B0C8YWSZ9S](https://www.amazon.co.jp/dp/B0C8YWSZ9S) | ←XIAO nrf52840の裏面パッドに合わせて細いものを選定しています。 |
| ニッパー | [https://www.amazon.co.jp/dp/B000TGJSWG](https://www.amazon.co.jp/dp/B000TGJSWG) | 部品の脚をカットするのに使用。なんでもOK。 |
| マスキングテープ | [https://www.amazon.co.jp/dp/B0FKSBYKV4](https://www.amazon.co.jp/dp/B0FKSBYKV4) | パーツ固定用。なんでもOK。 |
| プラスドライバー | [https://www.amazon.co.jp/dp/B002SQLEIG](https://www.amazon.co.jp/dp/B002SQLEIG) | M2ねじを回せるもの |
| フラックス | [https://www.amazon.co.jp/dp/B07MYZQSSR](https://www.amazon.co.jp/dp/B07MYZQSSR) | はんだ付けが楽になります |
| はんだ吸い取り線 | [https://www.amazon.co.jp/dp/B002TKEGRM](https://www.amazon.co.jp/dp/B002TKEGRM) | はんだ失敗時に活躍します |
| ピンセット | [https://www.amazon.co.jp/dp/B07BRSTLRQ](https://www.amazon.co.jp/dp/B07BRSTLRQ) | 使います |
| 耐熱マット | [https://www.amazon.co.jp/dp/B07T8G79DW](https://www.amazon.co.jp/dp/B07T8G79DW) | 机の保護に |
| キースイッチプラー、キーキャッププラー | [https://www.amazon.co.jp/dp/B0BFL6VW9Q](https://www.amazon.co.jp/dp/B0BFL6VW9Q) | キースイッチやキーキャップを取り外す器具 |
| 速乾性木工用ボンド | — | セラミック支持球の接着に使用します |
| つまようじ | — | 木工用ボンドの塗布に使用します |
| ウェットティッシュ | — | はみ出した木工用ボンドの拭き取りに使用します |
| USB-Cケーブル | — | ファームウェアの書き込みと有線での動作確認に使用します |

工具は各自の判断で省いていただいて結構ですが、1箇所はんだ付けの難易度が高い部品がありますので、**フラックスとはんだ吸い取り線**はご用意ください。

### ファームウェア

ファームウェアは以下からダウンロードしてPCに保存してください。

[ファームウェアをダウンロード](https://men-bou.net/content/files/2025/12/nape-rgbled_adapter-seeeduino_xiao_ble-zmk.uf2)

## パーツのはんだ付け

### キースイッチソケットの取り付け（難易度★）

![](images/socket-1.jpeg)

キースイッチソケットをPCBの裏面（Nape v1.0など印字がされている面）に実装します。SW1、SW2、SW3と記載のある3箇所です。はんだ付けは[こちら](https://www.youtube.com/watch?v=ehVMPcwq1AQ)の動画を参考にしてください。

※Napeで採用しているChocのスイッチソケットには正しい向きが決まっていますのでご注意ください。詳しくは[こちら](https://www.eisbahn.jp/yoichiro/2021/01/kailh_choc_v1_socket.html#gsc.tab=0)。

![取り付け後の参考図（1）](images/socket2-1.jpeg)

![取り付け後の参考図（2）](images/NapeBuildGuide_00006.jpeg)

*取り付け後の参考図*

### トラックボールセンサーの取り付け（難易度★★）

ボールの動きを読み取るセンサー（PMW3610）を取り付けます。

> [!NOTE]
> 発送時、センサーとレンズを組み合わせた状態で梱包しています。レンズの2本の脚を押し出して外してから作業してください。脚は折れやすいのでご注意ください。

センサーの取り付け向きにご注意ください。PCB裏面の「PMW3610」の印字と、センサーに記載されている文字の向きを合わせるように配置し、脚を差し込みます。

![](images/NapeBuildGuide_00007-1.jpeg)

奥まで差し込んだら、PCBから浮かないようにマスキングテープで固定します。

![](images/sensorMask-1.jpeg)

PCBの表側ではんだ付けします。フラックスを使ったほうがスムーズに作業できます。PMW3610は最大260℃までの温度、7秒以内でのはんだ付けが推奨されています。はんだごての温度を調整し、冷ましながらゆっくり実装してください。

![](images/NapeBuildGuide_00009.jpeg)

![](images/NapeBuildGuide_00010.jpeg)

![取り付け後の参考図](images/NapeBuildGuide_00011.jpeg)

*取り付け後の参考図*

はんだ付けできたら、センサーの保護シール2箇所を剥がします。

![](images/NapeBuildGuide_00012.jpeg)

付属のレンズを取り付けます。レンズには向きがあります。以下の写真に合わせて配置してください。

![](images/NapeBuildGuide_00013.jpeg)

![](images/NapeBuildGuide_00014.jpeg)

> [!NOTE]
> 個体差によってレンズが外れやすい場合があります。使用中にレンズがずれてしまうなど不具合がある場合は、**レンズの脚を溶かして固定できます。**ピンセットの端を介してはんだごてを押し付け、ゆっくり溶かしてください。やや難しい作業なので、不安な方はスキップしてください。

![](images/ashi_cap-1.jpg)

![](images/IMG_3670.jpg)

### XIAO nrf52840の取り付け（難易度★★★）

XIAO nrf52840（以後XIAO）はNapeの心臓部となる小さなコンピュータです。取り付けの難易度が高いので慎重に作業してください。

PCBの表側にXIAOを重ねます。その上から付属のピンヘッダ2つを穴に合わせて差し込みます。

※差し込みにはかなり力が必要です。怪我に気をつけて作業しましょう。

**※このピンヘッダははんだ付けしません。一時的な位置固定に使用します。**

![XIAOとPCBが隙間なく設置するようにします（1）](images/NapeBuildGuide_00015-1.jpeg)

![XIAOとPCBが隙間なく設置するようにします（2）](images/NapeBuildGuide_00016.jpeg)

![XIAOとPCBが隙間なく設置するようにします（3）](images/NapeBuildGuide_00017.jpeg)

*XIAOとPCBが隙間なく設置するようにします*

PCB裏面、四角い穴（スルーホール）が空いている箇所からはんだ付けします。  
まず、穴から見えるXIAOの2つのパッドにフラックスを塗布してください。

![](images/flux2-1.jpeg)

穴の角にある丸い切り欠きからハンダを流し込み、接地しているXIAO裏側のパッドに繋いでいきます。これを近接した2箇所で行うので、2つのパッドに流し込んだハンダが接触（ブリッジ）しないように気をつけてください。

以下の画像では、はんだごて（FX600）に付属のB型のこて先を使用。コテ先をXIAOのパッドに当てて熱を入れ、丸い切り欠きからはんだ（φ0.6mm）を差し込むようにするのがコツです。

![](images/throughHole-1.jpeg)

目視で確認し、完成画像と比較してブリッジしていないか確認してください。ブリッジした状態でバッテリーと繋いでしまうと、XIAOが壊れます。

![](images/NapeBuildGuide_00021_mod.jpeg)

もしブリッジしてしまった場合は焦らずはんだ吸い取り線を使ってやり直してください。

裏面はこのスルーホール部分のはんだ付けのみで完了です。表側に移ります。

まずピンヘッダを外します。まだ裏面の一部しかはんだ付けされていないので、必ずXIAO本体を押さえながら外してください。固くて平たいもので押し出すと簡単に外れます。

![](images/NapeBuildGuide_00022_mod.jpeg)

XIAO両側の各端子の側面とPCBのパッドをはんだ付けします。XIAO天面の穴まではんだが浸透する必要はありません。側面とパッドが繋がっていればOKです。

![](images/NapeBuildGuide_00023.jpeg)

![](images/NapeBuildGuide_00024.jpeg)

![取り付け後の参考図](images/NapeBuildGuide_00025.jpeg)

*取り付け後の参考図*

### スライドスイッチの取り付け（難易度★）

バッテリー駆動時に電源をオン・オフするためのスイッチを取り付けます。

PCBの裏面、「POWER」と印字のある箇所に、水平スライドスイッチを取り付けます。スイッチのツマミがPCBからはみ出す向きに配置し、裏面から脚を差し込んでください。

![スイッチのツマミがPCBの外にはみ出す向きに配置（1）](images/NapeBuildGuide_00031.jpeg)

![スイッチのツマミがPCBの外にはみ出す向きに配置（2）](images/NapeBuildGuide_00032.jpeg)

*スイッチのツマミがPCBの外にはみ出す向きに配置*

浮かないようにマスキングテープで固定します。

![](images/NapeBuildGuide_00033.jpeg)

PCBの表側から3本の脚をはんだ付けします。脚はできるだけ短くニッパーでカットしてください。

![](images/NapeBuildGuide_00034.jpeg)

![](images/NapeBuildGuide_00035.jpeg)

### タクトスイッチの取り付け（難易度★）

主にBluetoothやレイヤーの操作をするための裏面ボタンを取り付けます。

![](images/NapeBuildGuide_00026.jpeg)

PCB裏面に「RESET」と印字されている3箇所です。PCBの裏面から脚を差し込み、浮かないようにマスキングテープで固定します。

![](images/NapeBuildGuide_00027.jpeg)

![](images/NapeBuildGuide_00028-1.jpeg)

PCBの表側から脚をはんだ付けします。はんだ付けできたら脚はできるだけ短くニッパーでカットしてください。

![](images/NapeBuildGuide_00029.jpeg)

![](images/NapeBuildGuide_00030.jpeg)

### はんだ付け完了後の参考図

![](images/NapeBuildGuide_00036.jpeg)

![](images/result-1.jpeg)
## ケースの加工
### トップケースの加工
トップケース天面の穴に磁石を埋め込みます。
![](images/DSCF0451.jpeg)
固いもので強く押し込むことで埋め込むことができます。緩い場合は接着剤を使ってください。
![](images/DSCF0453.jpeg)

*露出する側の極性は二つとも同じ*になるように埋め込みましょう。こうすることで、後で加工するボールケースが向きに依存せずくっつくようになります。
![](images/DSCF0454.jpeg)
### ボールケースの加工
![](images/DSCF0455.jpeg)

裏面の穴に磁石を埋め込みます。まず、トップケースに埋め込んだ磁石にボールケース用の磁石をくっつけます。

![](images/DSCF0458.jpeg)
その上からボールケースを被せ、
![](images/DSCF0462.jpeg)
強く押し込みます。

![](images/DSCF0463.jpeg)
ボールケースを外し、裏面の磁石が奥まで入っているか確認してください。浅い場合は強く指で押し込んでください。

![](images/DSCF0464.jpeg)

セラミック支持球を接着します。
木工用ボンドを少量、つまようじで取り、ボールケースの内側のひし形の穴に塗ってください。

![](images/DSCF0465.jpeg)

![](images/DSCF0467.jpeg)

そこに支持球をのせ、ウェットティッシュなどではみ出すボンドをふき取りながら溝に支持球を強く押し込みます。
![](images/DSCF0471.jpeg)
![](images/DSCF0472.jpeg)
全3箇所に支持球をつけたら完了です。

### ボトムケースの加工
インサートナットを圧入します。
ボトムケースの四隅にある穴に、インサートナットを写真の向きに載せます。
![](images/DSCF0473.jpeg)
はんだごてを熱し（320℃くらい）、インサートナットの穴に垂直に押し当て、ボトムケースを間接的に熱で溶かしながら埋め込んでいきます。
![](images/DSCF0477.jpeg)
2/3ほど埋まったら、ひっくり返して耐熱の平たい面（3Dプリンタのビルドプレートなど）に押し当てることで、まっすぐ埋め込むことができます。
![](images/DSCF0478.jpeg)
## 組み立て

ケースを取り付けて組み立てます。

### トッププレートとPCBを合わせる

まずトッププレートの裏側の小さな穴からリセットボタンを通します。このリセットボタンはXIAOの表面にある小さなボタンを間接的に押すために使用します。

![](images/NapeBuildGuide_00038.jpeg)

![](images/NapeBuildGuide_00039.jpeg)

リセットボタンの上からPCBを合わせます。トッププレート裏面の溝にうまく合わせると隙間なく接地します。

![](images/NapeBuildGuide_00040.jpeg)

![](images/NapeBuildGuide_00041.jpeg)

指で押さえながら、トッププレートの表側からキースイッチを3つ取り付けます。ピンの向きをよく確認してカチッとハマるまで押し込んでください。写真の右端のキースイッチだけ取り付け向きが逆さなので注意してください。

![リセットボタンが外れないように押さえながら作業しましょう（1）](images/NapeBuildGuide_00042.jpeg)
![リセットボタンが外れないように押さえながら作業しましょう（2）](images/NapeBuildGuide_00043.jpeg)

*リセットボタンが外れないように押さえながら作業しましょう*

### トラックボールの取り付け

トッププレートのボールケースにトラックボールを押し込んで取り付けます。

![](images/NapeBuildGuide_00066.jpeg)

![](images/NapeBuildGuide_00044.jpeg)

![取り付け後の参考図](images/NapeBuildGuide_00047.jpeg)

*取り付け後の参考図*

### ファームウェアの書き込み

ケースを完全に組み上げる前に動作確認をします。

PCとXIAOのUSBポートをUSBケーブルで接続します。リセットボタンを2回続けて押します。うまく押せているとカチカチっと感触があります。

![](images/NapeBuildGuide_00046_mod.jpeg)

PCに「XIAO SENSE」という名前でXIAO内のストレージが認識されます。

![](images/20250323_201819.png)

「XIAO SENSE」にファームウェアのファイルをコピーすれば書き込み完了です。Macの場合「うまく書き込めませんでした」という旨の表示が出ますが、書き込めているので気にしなくて大丈夫です。

![](images/20250324_005131.png)

![Macの場合このエラーが表示されて「XIAO-SENSE」がアンマウントされるが、これでOK。](images/20250323_202329.png)

*Macの場合このエラーが表示されて「XIAO-SENSE」がアンマウントされるが、これでOK。*

### 有線での動作テスト

PCとケーブル接続した状態で動作確認します。キースイッチを指で押して反応するか確認してください。デフォルトではKey3が左クリック、Key2が右クリック、Key1が中クリックに設定されています。

![](images/keys.png)

ボールを転がしてカーソルが動くか確認してください。デフォルトでは下の写真の向きに設定されています。

![](images/GnNiPcMaIAA_NaH.jpeg)

※後述する設定方法でトラックボールの向きは変えられます。

キーだけが反応しない場合は、キースイッチを外してピンが曲がっていないか確認してください。

その他動作しないものがある場合は、以下のはんだ不良を疑います。トッププレートからキースイッチとPCBを取り外し、はんだ付けした箇所を目視で確認して怪しいところははんだ付けしなおしてください。

- トラックボールセンサー（PMW3610）の脚のはんだ部分
- XIAOの側面のはんだ部分
- キースイッチソケットのはんだ部分

### バッテリーの取り付け（無線で使用する場合）
電源スイッチがオフ状態（ツマミがPCBの外側にあればオフ）になっていることを確認します。

![](images/NapeBuildGuide_00048_mod.jpeg)

バッテリーの極性を確認します。写真のように**赤線が右側**になっていればOKです。バッテリーによってはこの極性が逆のものがあります。その場合はご自身でプラグを付け直し、修正してください。間違った極性のまま取り付けて電源を入れるとXIAOが壊れます。

![赤線が右側に来ていればOK](images/Nape---1.jpeg)

*赤線が右側に来ていればOK*

PCB裏面のコネクタにバッテリーのプラグを差し込みます。

![](images/Nape---2.jpeg)

### ボトムプレートへネジ止め

スイッチキャップとバッテリーをボトムプレートに配置します。バッテリーはケーブルが出ている方がUSBポート側に来るようにしてください。

![](images/Nape---3.jpeg)

トッププレートとボトムプレートを合わせます。以下の点を確認しながら合わせてください。

- バッテリーケーブルを挟んでいない
- スイッチキャップの溝に電源スイッチのツマミが収まる
- トッププレートとボトムプレートの間に隙間がない（PCBが引っかかる場合がありますが、軽く押し込むことでボトムプレートにピッタリ収まります）

![](images/NapeBuildGuide_00053.jpeg)

![](images/NapeBuildGuide_00052.jpeg)

![](images/NapeBuildGuide_00054.jpeg)

4箇所をネジ止めします。ネジの溝がナメないように注意してください。

![](images/NapeBuildGuide_00055.jpeg)

底面4箇所の溝に合わせてクッションゴムを貼ります。

![](images/NapeBuildGuide_00056.jpeg)

キーキャップを取り付けます。

![](images/NapeBuildGuide_00057.jpeg)

組み立て完了です。お疲れ様でした。

![](images/NapeBuildGuide_00058.jpeg)

## 「Nape」の使いかた

デフォルトファームウェアで使う場合のガイドはこちらをご覧ください。

[トラックボールつき自作キーボード「Nape」の使いかた](https://men-bou.net/nape-trackball-userguide/)

## キーマップを変更する

NapeはZMKファームウェアを使用しているため、キーマップ変更はカスタムファームウェアを作成して書き込む方法を推奨します。以下のガイドを参考にしてください。

[トラックボールつき自作キーボード「Nape」のカスタムファームウェアの作り方](https://men-bou.net/nape-firmware-guide/)

ZMKはZMK Studioというツールでファームウェアを書き換えずにキーマップ変更する方法も開発されていますが、まだ機能が少なく、マウスボタンなどの割り当てができないなど相性が良くありません。今後のZMKのアップデートをお待ちください。
