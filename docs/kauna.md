---
title: 買ってはならないものリスト
date: 2024-01-12
---

買わない理由

## 電脳

電子機器、電脳など
食べられないもの

### AMD Ryzen 3000番台(Matisse) CPU

https://www.amd.com/en/resources/product-security/bulletin/amd-sb-7014.html#affected-products
~~CVE-2023-31315の緩和策なし~~

2024年8月14日、この世代でも対応するように方針を改めた[^matisse-1]。

[^matisse-1]: https://www.amd.com/en/resources/product-security/bulletin/amd-sb-7014.html#revisions

### AMD Ryzen モバイルプロセッサ 6000番台(Rembrandt)と7000番台(Phoenix)

[Plutonに感染している](#microsoft-pluton)

### AMD Ryzen APU 5000番台(5700Gなど) (Cezanne or Renoir)

この3つの使用が重なると問題が起きる

- CPUは{Cezanne|セザンヌ} or {Renoir|ルノワール}
- PCIe 3.0 x16以上のグラフィックボード
- ハイレゾ対応ゲームまたはクリエイター向けサウンドデバイス

https://www.reddit.com/r/Amd/comments/11no3nd/a_detailed_summary_of_the_crackling_problem/?share_id=3BQ5oUoUiiOy_lFjkGIzx&utm_content=2&utm_medium=ios_app&utm_name=ioscss&utm_source=share&utm_term=1

### Intel CPU 第13世代と第14世代 Raptor Lake or Raptor Lake Refresh

ただ使っているだけで数週間～1年ほどで壊れる「焼損問題」というリコール級の重大な欠陥をかかえる。
ゲームをプレイ中にVRAMエラーなどが発生して落ちるようになる
やがてOSの起動もできないほどになり[^raptorlake-1]、UEFIの設定画面ですら落ちるようになる。
第12世代{Alder Lake|アルダーレイク}はセーフ、ただしAlderのリネームなものでも13世代(13000番台)ならアウト
特許侵害を指摘され13世代から変更された電圧制御が関係しているとされる。

[^raptorlake-1]: https://www.youtube.com/watch?v=38jxCharrwc

上記に伴いベンチマーク詐欺(焼損するほどの過剰なオーバークロック状態でのスコアをメディアを通じて宣伝)


### Intel

https://old.reddit.com/r/hardware/comments/1ei1zvm/intel_has_denied_two_of_my_14900k_rmas/
欠陥製品を売りつつ嘘をついたりしてまともに保証をしようとしない。

### AMD Radeon GPU

モニターのリフレッシュレートが60超過だとメモリクロックが最大になって下がらなくなり、アイドル消費電力がとても高くなる問題がある。
また動画再生中の消費電力がNVIDIA GeForceより高い
https://www.techpowerup.com/review/amd-radeon-rx-7900-xtx/37.html

### ASRock マザーボード

#### M.2 NVMeコネクタの欠陥

:::warning 情報求む
いつからいつまでの期間？
:::

コネクタに設計ミスがあり標準的なM.2 NVMe SSDを認識しない欠陥がある。
それについてまともにサポートもしなかった。
今でもどの製品に欠陥があるのか公式のアナウンスはない。
特にAM4までの製品には要注意。
最近のものではASRock B760M Pro RS/D4でもこの問題が報告された[^asrock-nvmessd-1]

[^asrock-nvmessd-1]: https://www.amazon.co.jp/gp/customer-reviews/R26ATWRTFMSU9I

#### TjMAXを無断で変更

:::warning 情報求む
いつからいつまでの期間？
:::

CPUのTjMAXを勝手に115℃に変更して動作させる。
これはメーカーの保証対象外となる行為である。

### MSI

批判的なレビューに対し削除を強要している[^msi-1]。

[^msi-1]: https://www.youtube.com/watch?v=O6BXwCJtaZE

BIOS設定項目の名前を独自のものに改名し、さも他社にはない機能のように見せている。

独自に電源の認証規格を作り、自社の製品を真っ先に登録して世界初とうたうなど、しょうもない。

#### MSI Intel用マザーボード

理由もなくBIOSの電圧制限の設定項目を非公開にしている[^msi-intel-motherboard-1]。

[^msi-intel-motherboard-1]: https://youtu.be/TmU3COA-32E?si=_KxeJi8BZsmUm3Nw&t=522

### Acer ラップトップ

Intel Core i9 13900HXなどHX付きのCPUを搭載したノートPCにて、HX付きであるにも関わらず電圧の変更を塞いでいる？[^acer-laptop-1]

[^acer-laptop-1]: https://www.techpowerup.com/forums/threads/i9-13900hx-dying-laptop.325785/post-5314653

### ASUSのグラフィックボード

北米ASUSのサポートは酷い。
[ASUS、ぼったくりの修理代金を請求。GeForce RTX 4090の16ピンコネクタの修理代がまさかの金額に](https://www.nichepcgamer.com/archives/asus-geforce-rtx-4090-16-pin-connector-repair-cost-is-a-rip-off.html)

### SSD

#### Western Digital SN850X

1日1回程度の頻度でWindowsがBSoDする不具合がある[^wd-sn850x-1]。

[^wd-sn850x-1]: https://forums.anandtech.com/threads/warning-about-wd-sn850x-nvme-drives.2607586/

#### Samsung SSD

https://www.phoronix.com/forums/forum/software/general-linux-open-source/1277056-samsung-860-870-ssds-continue-causing-problems-for-linux-users?p=1277159#post1277159
TRIMが動作しなかったりNCQが動作しなかったりバグが多い。

#### ADATA SX8100

故障報告多し。

#### SK hynix Platinum P41

数週間～数ヶ月で書き込み速度が大幅に低下する不具合があり、2024年8月22日現在もなお修正されていない。

#### Corsair製SSD

ファームウェアアップデートにWindows専用アプリケーションが必要である。

#### Corsair MP700

https://www.tomshardware.com/news/pcie-50-ssds-generates-errors-shut-down-without-cooler-fix-on-the-way

ヒートシンクを取り付けずに使うとデータが消失する重大な不具合がある。
ファームウェアアップデートで解消する。

#### Phison E26 コントローラを搭載したSSD

サーマルスロットリング制御に不具合があり、継続過熱すると強制シャットダウンを起こす。
ファームウェアアップデートで解消する。

#### Phison E21T コントローラを搭載したSSD

https://pcpartpicker.com/forums/topic/429279-reproducible-permanent-data-loss-on-phison-e21t-based-1-tb-m2-2230-ssds

データが消失する重大な不具合がある。
PCIeリンク速度を3.0に落とすことで回避できる。

### Samsung, OnePlus, Realme, Vivoスマートフォン

https://www.celsoazevedo.com/files/android/google-camera/troubleshooting/
すべてのカメラにアクセスできるアプリを恣意的に制限
※カスタムROMではアンロックされている

### Xiaomi スマートフォン 大陸版

HyperOSになってからChinaROMを搭載した中国向け端末(いわゆる大陸版)ではBootloader Unlockが困難になってしまった。
出荷時はMIUIだった機種でもあとからHyperOSをインストールしてしまうと手遅れ。

### Anker Eufy (監視カメラ)

所有者に無断でデータをクラウドサーバーに送信する[^anker-eufy-1]。
その事実を告発された際も嘘をついてまともに対応せず、さらには無断でデータを送信していることを少しわかりづらくする工作を行った[^anker-eufy-1]。

[^anker-eufy-1]: https://blog.kaspersky.co.jp/ip-cameras-unsecurity-eufy/33000/

それだけにとどまらず、Webページからプライバシーに関する文言を削除し開き直った[^anker-eufy-2]。

[^anker-eufy-2]: https://www.androidpolice.com/eufy-removes-privacy-language/

### Microsoft Pluton

Microsoftが開発したスケアウェア[^microsoft-pluton-1]。

[^microsoft-pluton-1]: https://semiaccurate.com/2022/01/18/amds-new-cpus-may-be-safe-to-deploy/

影響を受けるハードウェア:

- Qualcomm Snapdragon 8cx Gen 3
- AMD Ryzen モバイルプロセッサ 6000番台(Rembrandt)
- AMD Ryzen モバイルプロセッサ 7000番台(Phoenix)
- 搭載製品
  - Lenovo ThinkPad Z13[^microsoft-pluton-lenovo-thinkpadz13]

[^microsoft-pluton-lenovo-thinkpadz13]: https://www.phoronix.com/news/Lenovo-Pluton-Windows-Default

### 行儀の悪いソフトウェア

アンインストールしても残骸を残していく。

:::tip
Geek Uninstaller は残骸を消すことができます。
:::

#### DMMの花札のやつ

> 398 Socket774 (ﾜｯﾁｮｲ df58-mfjK) sage 2024/01/07(日) 14:15:25.48 ID:hi4U8DD80
> DMMの花札のやつあるでしょ。あれアンインストールしてもUnityのフォルダに残ったまま。
> Cドライブ強制どころか一部のゲームはアンインストールしても全部残してるから要注意
>
> SteamでもヘブバンはCドライブやね。ジャップメーカーさあ

#### 筆王ZERO

永年アップデート無料と言いながらOSが変わる度に買わされてWin11には非対応になった

### Linux

2024年10月18日、Linus Torvalds氏はロシアの電子メールアドレスを持つカーネルチーム12名を理由なく外した。
さらにTorvaldsはこれに対する批判を「ロシアの荒らし」によるものだと妄想している。[^linux-1][^linux-2]

[^linux-1]: https://www.hardwareluxx.de/index.php/news/allgemein/netzpolitik/64734-linus-torvalds-russische-entwickler-aus-linux-kernel-team-entfernt.html
[^linux-2]: https://linuxnews.de/linux-entfernt-russische-entwickler/

### オンラインサービス

#### CloudFlare DNS

archive.todayを解決できない

#### GIGAZINE

https://mevius.5ch.net/test/read.cgi/internet/1554553882/808
> 808 192.168.0.774 sage 2022/06/16(木) 06:39:41.81 ID:sQjnP0OR0
> 今年だけで既に9本の記事にWayback MachineのURL貼ってるな、GIGAZINEさんは。
> 右手でアーカイブURLを貼りながら、左手ではブルースター・ケールに中指突き立てて削除要請という絵面。

WaybackMachineでのアーカイブを拒否している。
しかもその上で記事中にWaybackMachineのURLを使う矛盾した行動は見るに耐えない。

#### ASCII.jp

インテルの場合、不具合は一切報道せずBIOS配布でやっと記事
[AMDは電光石火で記事を書く](https://web.archive.org/web/20240805083459/https://ascii.jp/elem/000/004/214/4214050/)

さすがにまずいと思ったのかすぐにタイトルだけは修正したようだ。

#### PayPal, Flattr

ロシア国民であるというだけで送金を停止した[^lftp-top]。
[^lftp-top]: https://lftp.yar.ru/

#### Firefoxに非対応

ニコニコチャンネル
https://help.nicochannel.jp/hc/ja/articles/4414639503513
> [ブラウザ]
> Microsoft Edgeの最新版（正式版）
> Google Chromeの最新版（正式版）

MSI
https://jp.msi.com/Motherboard/MAG-X670E-TOMAHAWK-WIFI/support
> IOSやドライバのダウンロードの際には、ChromeあるいはEdgeのご利用をお勧めします。

### Platform Tilt

https://mozilla.github.io/platform-tilt/

- Apple
- Google
- Googleアプリ
- Google検索

### Instagram

年齢が13歳以下の方の利用を禁止している。

### ゲーム

#### Call of Duty BO4, Call of Duty MW 2019, Call of Duty MW3

https://github.com/ValdikSS/GoodbyeDPI/issues/148
https://www.youtube.com/watch?v=eOViixWjNIQ
ロシアなどに都合の悪い情報を検閲する「DPI」を回避するプログラムが動作している場合、起動を拒否する
本来はアンチチート用のプログラムであるRICOCHETがこの動作を行っていると推測されている。

### DELL

顧客情報をずさんに管理して流出させた上に我々も被害者ムーブ
https://www.bleepingcomputer.com/news/security/dell-api-abused-to-steal-49-million-customer-records-in-data-breach/

## 自動車

ぶーぶ
食べられないもの

### デンソー 第3世代CAN搭載

![CAN通信の世代](https://ipfs.io/ipfs/QmT82F6MFktN6vE7hN6PwxsCucPQriypDU5SgmkSiVWzZB?filename=denso-can-generations.png)
出典: https://youtu.be/LQiUO2MWXXk?si=wWFzpp1QAzagRuv3&t=490

- トヨタ
- マツダ
  - CX-60

絶対に接続してはいけない、デバッグ用のUSB Type-Cポートが露出しており、知らずに充電用だと思ってスマートフォンなどを接続してしまうと最悪の場合セーフモードに入ってしまい修理に100万円以上の高額な費用がかかる。

### ワンタッチウインカー搭載車

*ダイハツウインカー*と{巷|ちまた}で呼ばれる、混乱しやすい不親切な動作で悪名高い風変わりなウインカーを搭載したクルマが増えてきている。

通常のウインカーは「上」「中」「下」の3つの位置があり、レバーの位置を動かして移動することでウインカーの作動状態を指定できる直感的で馴染み深いものである。
一方でダイハツウインカーでは上や下に入れてもそのまま位置が固定されず中に戻ってしまう。
(レバーというよりスイッチと言う方が近いものになっている。)
これを止めるには通常のウインカー同様にステアリング(ハンドル)を戻す(出している方向とは逆側にステアリングを切る)ことによる自動的な消灯で止められるが、手動で消したい場合は**現在出している方向とは逆側に対してわずかに動かす**という操作が必要。
出すのは簡単だが止める方法が直感でわからない。

ウインカーを出しっぱなしにして直進し続けるクルマを最近見かけるのはこれのせいだとも言われる。
実際に方向指示器をつけっぱなしにして直進した自動車による事故も起きており危険である。^[要出典]^

https://www.youtube.com/watch?v=YgawxLAqCNc

## 食品

食べられるけど食べちゃだめなもの

### スクロース
高いう蝕性、反栄養素(反糖質)
強いう蝕性
摂取するほどインスリン抵抗性が亢進してしまう
💡代替品
甘味料→✅イソマルツロース
その他非還元糖→✅トレハロース

### フルクトース
反栄養素(反糖質)
スクロースよりう蝕性は少しだけマシだがそれ以外はより悪い
特にグルコースと併存すると吸収速度が2倍になるため果糖ぶどう糖液糖はなかなかの毒性
💡代替品
甘味料→✅イソマルツロース、トレハルロース
デンプンの老化促進→✅イソマルトデキストリン

### ニップン

イソマルトオリゴ糖の商品ページにて科学的根拠のない宣伝を行う
※ニッ○ンという会社はいくつもあるので間違えないように
2024年5月12日現在: Amazonの販売ページが削除されたのか商品そのものが販売停止になったのか、検索してもヒットしない。

### 大塚食品

- https://www.youtube.com/watch?v=N7iPJScGcrs
- https://www.youtube.com/watch?v=ipIj5ACAzS4

## 地域

### 名古屋市名東区

https://www.youtube.com/watch?v=uMB72vFhdPY
