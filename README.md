# Karabiner ommit-nicola.json

## 概要

ommit-nicola.jsonは、Karabiner-Elementsを使って親指シフト入力をするための設定ファイルである。

## 特徴

これは、下記のような特徴を持った親指シフト入力をするための設定である。

* NICOLA規格の配列をベースに一部のキーを省略している。
* Qwerty配列のキーボードで、OSの設定でDvorak配列に変更した状態で使うことを想定している。
* 親指シフトキーは、lang8, lang9を使用する。
* 英数とかなの切り替えは、lang8, lang9のダブルタップを利用する。

### 親指シフトの配列

基本的にはNICOLA配列をベースにしている。しかし、キーが少ないキーボードを利用する想定であるため、必要最小限のキーだけ定義している。

* 最上段の数字キーは未設定。
  * 記号類については、記号キーをそのまま使って入力する。
* 右手上段小指にあるカンマ「，」を読点「、」に置き換える。カンマは未設定。
* 右手小指のホームポジションから右側は未設定。
* 日本語のかな漢字変換は、スペースキーで行う。

### キーボードの配列

作者の利用してきた環境の歴史的な経緯によって、下記の環境を想定している。

* 物理的な配列はQwerty配列。
* 論理的な配列はDvorak配列。
  * OSの設定でQwerty配列からDvorak配列に変換。

これにより、Karabiner-Elementsが送受信するキーコードはQwerty配列のものとなる。そして、論理的にはDvorak配列を使用しているため、ローマ字入力に使うためのアルファベットのキーコードは、Dvorak用に変換されてInput Methodに送られる。

例えば「か」を入力するためには、Karabiner-Elementsは、"k", "a"を送るのではなく、"v", "a"を送らないといけない。Dvorak配列における"k"は、Qwerty配列で"v"の位置にあるためである。

なお、これについてはあくまで暫定的な措置で、将来的には、キーボード側でDvorak配列に対応し、OS側での変換をせずとも利用できるようにする予定である。

### 親指シフトキーのキーコード

一般的に、日本語配列キーボードを持つmacにおいて、親指シフト入力のシフトキーに使われているキーは、位置的に「英数キー」や「かなキー」ではないかと思う。英語配列キーボードだと、スペースやコマンドキーが利用されているかと思う。

自分が利用しているキーボードは、QMK Firmwareを使ってキーカスタマイズができるため、通常は利用されていないlang8, lang9を親指の位置で使えるようにし、それをシフトキーに割り当てている。その理由は、本来はシフトキーは独立しているためである。また、シフトキーの同時打鍵に失敗すると、意図せず英数モードに切り替わってしまうことがあり、それを防止するためである。

なお、ラップトップ型のキーボードを直接利用する場合は、lang8, lang9は使えないため、英数キーとかなキーを利用する。

### 英数入力モードとかな入力モードの切り替え

英数キーとかなキーは、それぞれ独立した別のキーとして配置している想定ではあるが、歴史的経緯により、親指シフトキーを単体でダブルタップしても切り替えできるようにしている。しばらく試した感じでは、そうそう暴発しないようなので、有効にしている。これと同様の設定であれば、親指シフト専用のキーを用意しなくとも良いかもしれない。

## LICENSE

The configuration file is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
