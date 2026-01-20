---
title: 買ってはならないものリスト
date: 2024-01-12
---

買わない理由

## 電脳

電子機器やコンピュータなど。

### AMD Ryzen 3000番台(Matisse) CPU

https://www.amd.com/en/resources/product-security/bulletin/amd-sb-7014.html#affected-products
~~CVE-2023-31315の緩和策なし~~

2024年8月14日、この世代でも対応するように方針を改めた[^matisse-1]。

[^matisse-1]: https://www.amd.com/en/resources/product-security/bulletin/amd-sb-7014.html#revisions

### AMD Ryzen モバイルプロセッサ 6000番台(Rembrandt)と7000番台(Phoenix)

[Plutonに感染している。](#microsoft-pluton)

### AMD Ryzen APU 5000番台(5700Gなど) (Cezanne or Renoir)

この3つの使用が重なると問題が起きる

- CPUは{Cezanne|セザンヌ} or {Renoir|ルノワール}
- PCIe 3.0 x16以上のグラフィックボード
- ハイレゾ対応ゲームまたはクリエイター向けサウンドデバイス

https://www.reddit.com/r/Amd/comments/11no3nd/a_detailed_summary_of_the_crackling_problem/?share_id=3BQ5oUoUiiOy_lFjkGIzx&utm_content=2&utm_medium=ios_app&utm_name=ioscss&utm_source=share&utm_term=1

### Intel CPU 第13世代と第14世代 Raptor Lake or Raptor Lake Refresh

ただ使っているだけで数週間～1年ほどで壊れる「焼損問題」というリコール級の重大な欠陥がある。
初期症状はゲームをプレイ中にVRAMエラーなどが発生して落ちるようになる。
進行するとやがてOSの起動もできないほどになり[^raptorlake-1]、UEFIの設定画面ですら落ちるようになる。
第12世代{Alder Lake|アルダーレイク}はセーフ、ただしAlderのリネームなものでも13世代(13000番台)ならアウトかもしれない。

[^raptorlake-1]: https://www.youtube.com/watch?v=38jxCharrwc

上記に伴いベンチマーク詐欺(焼損するほどの過剰なオーバークロック状態でのスコアをメディアを通じて宣伝)。

最新のマイクロコードの*0x12F*では修正したとしているが、何度も修正したと言ってはまた新しいバージョンを出して今度こそ本当に修正したを繰り返している。

### Intel

https://old.reddit.com/r/hardware/comments/1ei1zvm/intel_has_denied_two_of_my_14900k_rmas/
欠陥製品を売りつつ嘘をついたりしてまともに保証をしようとしない。

### AMD Radeon GPU

モニターのリフレッシュレートが60超過だとメモリクロックが最大になって下がらなくなり、アイドル消費電力がとても高くなる問題がある。
また動画再生中の消費電力がNVIDIA GeForceより高い。
https://www.techpowerup.com/review/amd-radeon-rx-7900-xtx/37.html

### ASRock マザーボード

#### M.2 NVMeコネクタの欠陥

:::warning 情報求む
いつからいつまでの期間？
:::

設計ミスがあり標準的なM.2 NVMe SSDを認識しない欠陥がある。
それについてまともにサポートもしなかった。
どの製品に欠陥があるのか公式のアナウンスは見つけられなかった。
特にAM4までの製品は要注意とされる。
最近のものではASRock B760M Pro RS/D4でもこの問題が10人以上のユーザーから報告されている[^asrock-nvmessd-1]。

[^asrock-nvmessd-1]: https://www.amazon.co.jp/gp/customer-reviews/R26ATWRTFMSU9I

> ASRock Japan @AsrockJ
> 現状の各最新BIOSでは動作確認が取れました！
> 新型マザーボードにはサポートリストにも記載予定となっております。
> 原因としましてはGNDの位置が一般的なマザーボードとは異なっているためBIOS上認識しなかったとBIOSチームから連絡ありました。なかなか特殊なSSDとのことです！
https://x.com/AsrockJ/status/1358360196532170752

#### TjMAXを無断で変更

:::warning 情報求む
いつからいつまでの期間？
:::

CPUのTjMAXを勝手に115℃に変更して動作させる。
これはメーカーの保証対象外となる行為である。

#### TDC・EDCを無断で変更し焼損

ミドルクラス以上のAM5マザーボードにてCPUのTDC・EDCを勝手に規定値より上げオーバークロックして動作させていた。
これによってCPUが焼損してしまう事態となってしまった。

### MSI

批判的なレビューに対し削除を強要している[^msi-1]。

[^msi-1]: https://www.youtube.com/watch?v=O6BXwCJtaZE

独自に電源の認証規格を作り、自社の製品を真っ先に登録して世界初とうたうなど、しょうもない。

#### マザーボード

セキュアブートがバグっていて機能しないまま2024年12月6日現在も放置されている。

BIOS設定項目の名前を独自のものに改名し、さも他社にはない機能のように見せている。

X870Eチップセットのマザーボード(Tomahawkを除く)において、M.2がPCIe 1.0接続になってしまう不具合が放置されている。
それに対し(再現率100％にも関わらず)問題が確認できなかったとしてサポートをつっぱねている[^msi-x870e-m2]。

[^msi-x870e-m2]: https://www.reddit.com/r/MSI_Gaming/comments/1it8g5x/comment/mkzuq7p/

#### Intel用マザーボード

理由もなくBIOSの電圧制限の設定項目を非公開にしている[^msi-intel-motherboard-1]。

[^msi-intel-motherboard-1]: https://youtu.be/TmU3COA-32E?si=_KxeJi8BZsmUm3Nw&t=522

### ASUS PCIe Slot Q-Release Slim搭載のマザーボード

この機構には脱着の際にカードが引っかかり端子部分を削り取ってしまう欠陥がある[^asus-q-release-slim-1][^asus-q-release-slim-2][^asus-q-release-slim-3]。

[^asus-q-release-slim-1]: https://videocardz.com/newz/asus-pcie-slot-q-release-slim-mechanism-may-scratch-your-gpu-first-rtx-5090-affected
[^asus-q-release-slim-2]: https://www.bilibili.com/video/BV1UefJYtEUy/
[^asus-q-release-slim-3]: https://x.com/aschilling/status/1882688162008650071

### Acer ラップトップ

Intel Core i9 13900HXなどHX付きのCPUを搭載したノートPCにて、HX付きであるにも関わらず電圧の変更を塞いでいる？[^acer-laptop-1]

[^acer-laptop-1]: https://www.techpowerup.com/forums/threads/i9-13900hx-dying-laptop.325785/post-5314653

### ASUSのグラフィックボード

北米ASUSのサポートは酷い。
[ASUS、ぼったくりの修理代金を請求。GeForce RTX 4090の16ピンコネクタの修理代がまさかの金額に](https://www.nichepcgamer.com/archives/asus-geforce-rtx-4090-16-pin-connector-repair-cost-is-a-rip-off.html)

#### PRIME RTX 5070 Ti および TUF RTX 5070 Ti

ベイパーチャンバーは実際には搭載されていない[prime-tuf-rtx5070ti]。

[prime-tuf-rtx5070ti]: https://reddit.nerdvpn.de/r/ASUS/comments/1kx27ea/psa_asus_rtx_5070_ti_prime_and_tuf_models_do_not/

### Inno3Dのグラフィックボード

ファンが必ず経年劣化で壊れる。
またステッカーを剥がせば保証が無効になるという違法な保証規定が記されてある。[^inno3d-graphicsboard]

[^inno3d-graphicsboard]: https://www.youtube.com/watch?v=Sk_aZg9ZvTU

### NVIDIA GeForce RTX 3060 Ti でHynix製のメモリチップを搭載しているグラフィックボード

数年使用するとゲーム中に画面が暗転しクラッシュする不具合が発生する可能性がある[^nvidia-geforce-rtx-3060-ti]。

このグラフィックボードには3種類のメモリチップが存在しており、そのうちのHynix製メモリが搭載されていた場合に問題が生じる。

- Hynix
  - 第1世代
  - 第2世代
  - 第3世代
- Micron
- Samsung

Hynix製メモリには第1世代～第3世代まであり、第1世代にもっとも顕著に問題が生じる。
特に*Hynix X005*と呼ばれるチップに問題があるとされていたが、後にすべてのHynix製メモリチップに問題があると判明した。
第2世代以降はマシになっているものの遅かれ故障する。

このグラフィックボードに搭載できる最高のメモリチップはSamsung製のものでありオーバークロック耐性も高い。

[^nvidia-geforce-rtx-3060-ti]: :vhs: https://www.youtube.com/watch?v=d_dcdT_I25Q

### NVIDIA RTX 5000番台 (Blackwell) GPU

32BitのOpenCLとCUDAおよびPhysXのサポートが削除された。

> GeForce RTX 50 Series から 32bit な CUDA/OpenCL が切られたことにより patch.aul の fast.cl が無効化されてしまう事態が Twitter や 2ch などで散見されてるな
> 
> それによりB系を入れられちゃうのは避けたい気がするが、そもそも 32bit サポートがハードウェア側からどんどん切られていく気がするなという
> 
> やA滅

https://misskey.io/notes/a7gaywvfpo9o06bz

### GIGABYTE製のRTX5000番台・RX9000番台のグラフィックボード

サーマルパッドの代わりにサーマルゲルが使用されているのだが、それが縦向きにされただけで垂れてきてしまう問題がある。

### SSD

#### Western Digital SN850X

Windowsにおいてブルースクリーンが1日1回程度の頻度で起こる[^wd-sn850x-1]。

[^wd-sn850x-1]: https://forums.anandtech.com/threads/warning-about-wd-sn850x-nvme-drives.2607586/

#### Samsung SSD

https://www.phoronix.com/forums/forum/software/general-linux-open-source/1277056-samsung-860-870-ssds-continue-causing-problems-for-linux-users?p=1277159#post1277159

##### Samsugn 860 870 EVO SSD

連続的TRIMが壊れている。
またAMDチップセット下ではNCQも不具合を起こす。[^samsung-860-870-evo-1]

LinuxやWindowsでは応急処置としてこの機種ではTRIMもNCQも無効-になるので基本的な動作は可能である。
ただしNCQが無効になるとパフォーマンスが低下してしまう。[^samsung-860-870-evo-1]

:::info
TRIMコマンドには定期的TRIMと連続的TRIMの2種類がある。
Windowsは定期的TRIMにのみ対応、Linuxではどちらも対応している。
:::

[^samsung-860-870-evo-1]: https://www.phoronix.com/news/Samsung-860-870-More-Quirks

#### Crucial SSD

型番を変えずにサイレント仕様変更を繰り返している。
またレビュアーに高速な仕様のものを配布してからこっそり部品をダウングレードして性能を低下させるなどの詐欺を行っている。[^crucial-1]

[^crucial-1]: https://www.extremetech.com/computing/325824-buyer-beware-crucial-swaps-p2-ssds-tlc-nand-for-slower-inferior-qlc-chips

##### Crucial MX500

最新のファームウェア「M3CR046」にバッファオーバーフローの脆弱性がある[^crucial-mx500-m3cr046]。

[^crucial-mx500-m3cr046]: https://www.techpowerup.com/326587/crucial-mx500-ssd-firmware-m3cr046-vulnerable-to-buffer-overflow-attacks

##### Crucial T500

[:vhs: Gen4最強SSDのCrucial T500、書き込み遅すぎ問題は最新ファームウェアで解決したの？　⇒してませんでした。2024年10月末ファームウェア検証結果の備忘録](https://www.youtube.com/watch?v=Hc7EWOnFuRM)

連続で書き込みを行うと約330MB/s程度にまで速度が落ちてしまう。

#### ADATA SX8100

故障報告多し。

#### SK hynix Platinum P41

数週間～数ヶ月で書き込み速度が大幅に低下する不具合があり、2024年8月22日現在もなお修正されていない。

#### Corsair製SSD

ファームウェアアップデートにWindows専用アプリケーションが必要である。

#### ORICO O7000 SSD

NANDをTLCからQLCへ無断で切り替えている。
[:vhs: とある噂を聞いて格安ハイエンドSSDを買ってみたら要注意な事実が判明！ORICO O7000(2TB)　2回目レビュー](https://www.youtube.com/watch?v=IIuxjwZ8Utk)

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

### Sony PC TV Plus

> SSDの価格変動に右往左往するスレ214台
> https://egg.5ch.net/test/read.cgi/jisaku/1730652845/978
> 978: Socket774警備員[Lv.7][新芽]   2024/11/26(火) 22:41:54.62 ID:cKeayL6h
> ちなみにシステムドライブにSATASSD使った理由はソニーのPCTVPLUSという糞アプリがTV見ている間ずっとCドライブに書き込んでくクソ仕様なのがわかって
> YMTC232M.2使うの勿体ないから安物にしたくて切り替えた

> https://egg.5ch.net/test/read.cgi/jisaku/1730652845/982
> 982: Socket774警備員[Lv.7][新芽]   2024/11/26(火) 22:59:58.37 ID:cKeayL6h
> \>>980
> 改善要望はソニーに出しておいた
> Cドライブ固定じゃなくて設定で切り替えられるようにしろと
> Cドライブは最近書き込み寿命のあるSSDほとんどなんだからと
> 
> 2MB/sくらい書き込むんよ
> それ以外は使い勝手悪くないアプリなんだけどね

### GameSir

Amazonレビューで低評価をすると返金するからレビューを削除しろと要求してくる。

### Nimaso

Amazonレビューで低評価をすると返金するからレビューを削除しろと要求してくる。[^nimaso-1]

[^nimaso-1]: https://x.com/aoshijima/status/1865182632088404225

### Logicool

動作に必要になる[「G HUB」](https://gaming.logicool.co.jp/ja-jp/innovation/g-hub.html)という(Windows・MacOS専用の)常駐ソフトには、TEMPフォルダを別のドライブに設定していると起動しなくなるバグがバージョン2024.6から2025年6月現在まで放置されている[^logicool-ghub]。

[^logicool-ghub]: https://www.reddit.com/r/LogitechG/comments/1et5frr/last_update_of_ghub_broke_it_so_much_that_you/

### Procolored製のプリンター

マルウェアに感染したドライバーを配布していた。
その上、報告に対してマルウェアには感染していないと嘘の返答をして取り合わなかった。[^procolored-1][^procolored-2]

[^procolored-1]: https://www.gdatasoftware.com/blog/2025/05/38200-printer-infected-software-downloads
[^procolored-2]: https://www.reddit.com/r/computerviruses/comments/1kbkmgq/viruses_included_in_product_im_reviewing/

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

### Kaldaien氏

多数のゲームフォーラムからBANされた上に、モデレーターを批判しており完全に自分は正しいと確信している。[^kaldaien-1]

[^kaldaien-1]: https://steamcommunity.com/discussions/forum/7/2798376099468450321/

#### Special K

Kaldaien氏を開発チームに採用している。
以前はSteam上でも配信されていたが、ValveからBANされた経緯を持ついわくつきでもある。[^special-k-1]

[^special-k-1]: https://steamcommunity.com/games/1157970/announcements/detail/2725193056674812318

### Vencord

[Vencord](https://github.com/Vendicated/Vencord)

開発者のVendicated氏が母国語が英語でないものを嫌って迫害している。

元々はVencordの[*Translate*](https://github.com/Vendicated/Vencord/tree/main/src/plugins/translate)というプラグインは多言語から多言語への翻訳に対応していたが、どういうわけかある時(おそらく2023年9月頃)から英語への翻訳以外はできないよう恣意的に仕様変更されてしまった[^vencord-2]。

[^vencord-2]: https://sakkuntyo.github.io/2023/09/27/vencord-translater-change-language/

これに対するIssueには「ignored contributor requirement」「invalid」というタグを付けて拒絶してしまっている[^vencord-1]。

[^vencord-1]: https://github.com/Vendicated/Vencord/issues?q=is%3Aissue%20state%3Aclosed%20translate

またソフトウェア自体もUIのi18n対応を拒絶している[^vencord-3]。

[^vencord-3]: https://github.com/Vendicated/Vencord/issues/933

:::info
[GitHub](https://github.com/)では[SettingsのModeration](https://github.com/settings/blocked_users)よりユーザーのブロックが行える
:::

:::info
[Equicord](https://github.com/Equicord/Equicord)が2025年11月20日現在主流のプラグインエコシステムのようです。
こちらはよりプラグインが充実しており[多言語対応の翻訳プラグイン]もあります。
:::

### Brave

https://www.reddit.com/r/browsers/comments/1j1pq7b/list_of_brave_browser_controversies/

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

#### PayPal

突如として^[いつ？]^Steamでの決済サービスを停止した[^paypal-1]。
この件について問い合わせたところカスタマーサポートが「Steam側がPayPalを停止した」と嘘をついたという報告もある[^paypal-2]。

[^paypal-1]: https://web.archive.org/web/20250812121247/https://help.steampowered.com/en/faqs/view/731C-13C7-7D04-A11E
[^paypal-2]: https://www.youtube.com/watch?v=AZVJGtvY1js

アカウントを解約しようとすると条件に本人確認書類を提出を求めてくる。

#### PayPal, Flattr

ロシア国民であるというだけで送金を停止した[^lftp-top]。
[^lftp-top]: https://lftp.yar.ru/

#### Visa, Mastercard

Steamで性的なコンテンツを配信するのをやめるように圧力をかけた。^[要出典]^

#### DLsite

AI生成でないコンテンツを頑なにAI生成だと言い張って作品の登録を拒む。[^dlsite-1]

[^dlsite-1]: https://x.com/charon_kn/status/1957799893382361177

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

オリジナルの動画を投稿しただけで何故かBANする。

### ゲーム

#### Call of Duty BO4, Call of Duty MW 2019, Call of Duty MW3

https://github.com/ValdikSS/GoodbyeDPI/issues/148
https://www.youtube.com/watch?v=eOViixWjNIQ
ロシアなどに都合の悪い情報を検閲する「DPI」を回避するプログラムが動作している場合、起動を拒否する
本来はアンチチート用のプログラムであるRICOCHETがこの動作を行っていると推測されている。

#### Grand Theft Auto V (GTAV, GTA5)

https://www.urizo.top/index.php/2024/10/31/record-of-the-gta-online-fake-ban-incident/

2023年12月～2024年1月にかけて、一部の中国のプレイヤーは無実の罪で奇妙なBANを受けた。

これは*Fake-BAN*と呼ばれる、通常とは異なる異様なものであった。
(詳細は元の記事を参照)

この措置はRockstarのポリシーに反するものである上、いかなる声明や説明も行っていない。
サポートに連絡してもテンプレ回答を返されるのみでまともに取り合ってもらえないようだ。

公開セッションに行かずに招待限定セッションでのみプレイしていた人だけは被害を受けなかったという。

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

### トヨタ GRカローラ

走行中にエンジンが火を吹く事故が発生した。
その際に支離滅裂な言い訳を声明として残した。[^toyota-grcorolla-1]

[^toyota-grcorolla-1]: https://www.theautopian.com/toyota-reportedly-blames-tires-for-spontaneous-gr-corolla-engine-explosion-and-fire-which-makes-no-sense-whatsoever/

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

### アサヒ食品グループ

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【閲覧注意】<br>アサヒグループ食品いつものおみそ汁からクワガタの頭のようなものが出てきた。<br><br>数日体調不良になっていたので、本社に問い合わせたら対応がまさかのQUOカード300円で納得いかない<br><br>商品自体800円程なのに小分けの1袋分しか帰ってこなかった<br> <a href="https://twitter.com/hashtag/%E7%95%B0%E7%89%A9%E6%B7%B7%E5%85%A5?src=hash&amp;ref_src=twsrc%5Etfw">#異物混入</a> <a href="https://twitter.com/hashtag/%E6%8B%A1%E6%95%A3%E5%B8%8C%E6%9C%9B?src=hash&amp;ref_src=twsrc%5Etfw">#拡散希望</a> <a href="https://twitter.com/hashtag/%E4%BC%81%E6%A5%AD%E5%AF%BE%E5%BF%9C?src=hash&amp;ref_src=twsrc%5Etfw">#企業対応</a> <a href="https://t.co/9r0sYQGhbM">pic.twitter.com/9r0sYQGhbM</a></p>&mdash; Len (@MELTDOWN_Na) <a href="https://twitter.com/MELTDOWN_Na/status/1912859323249959024?ref_src=twsrc%5Etfw">April 17, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

![QUOカード300円分](https://pbs.twimg.com/media/GovXah8bMAAcRBj?format=jpg&name=orig)
![クワガタの頭のようなもの](https://pbs.twimg.com/media/GovXah3aAAAvG5W?format=jpg&name=orig)

味噌汁からクワガタの頭のようなものが出て数日体調不良に見舞われたものの、対応がたったのQUOカード300円だけ。

### ニップン

イソマルトオリゴ糖の商品ページにて科学的根拠のない宣伝を行う
※ニッ○ンという会社はいくつもあるので間違えないように
2024年5月12日現在: Amazonの販売ページが削除されたのか商品そのものが販売停止になったのか、検索してもヒットしない。

### 大塚食品

- https://www.youtube.com/watch?v=N7iPJScGcrs
- https://www.youtube.com/watch?v=ipIj5ACAzS4

## 会社

### RIAA

RIAAにはUMG、Capitol Records、Concord Bicycle Assets、CMGI Recorded Music Assets、Sony Music Entertainment、Arista Musicが含まれる。

Internet Archiveに対して訴訟を行っている[^ia-1][^ia-2]。

[^ia-1]: https://blog.archive.org/2025/04/17/take-action-defend-the-internet-archive/
[^ia-2]: 

GamersNexusのニュース: [📼Tip Line - Microsoft Recall Bypass, Burning Battery Banks, Right to Repair Laws](https://youtu.be/jAy3BT0PLEg?t=302&si=-MCI0XHibAzS2fSl)

## 地域

### 名古屋市名東区

https://www.youtube.com/watch?v=uMB72vFhdPY

### 海外の牛乳、およびそれを用いた加工品

日本以外では家畜の牛への成長ホルモンの投与が禁止されていないため、牛乳の成長ホルモンの含有量が高い。
この成長ホルモンこと*インスリン様成長因子(IGF)*は皮脂の分泌を増やすなど悪影響がある。

### オーストラリア

インターネットの利用が規制されている。
あなたはオーストラリア産の商品を購入したくないかもしれない。

### 中華人民共和国(中国)

インターネットの利用が規制されている。
あなたは中国産の商品を購入したくないかもしれない。
