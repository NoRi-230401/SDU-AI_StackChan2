# SDU-AI-StackChan2

robo8080さん作成 AI-StackChan2 ソフトに次の修正を行いました。<br>
- rootCACertificate.h更新(2024-07-10)</b>
- ChatGPTのモデル変更 "gpt-4o-mini" 
- SD-Updater対応<br>
- サーボPortを外部ファイル（servo.txt）で設定。<br>
<br>
<b>SD-Updaterに対応した AiStackChan2 です。</b><br>
ブート時に、SD_Updater用の画面が立ち上がります。<br>
SDに入れた他のソフトを切り替えることができるようになります。<br>
<br>


## 設定ファイル
apikye.txt, wifie.txtは、AI-StackChan2と同じです。

<b>新規に "servo.txt"　をSD直下に設置してください。</b><br>
サーボモーターを使用するGPIO番号等の値を設定してください。
- servo.txt :  Servo設定用ファイル<br>
１行目(USE_SERVO)   ： "on" (使用する)　または、 "off"（使用しない）<br>
２行目(SERVO_PIN_X) ： "13"(PortC)　または、"33"(PortA)<br>
３行目(SERVO_PIN_Y) ： "14"(PortC)　または、"32"(PortA)<br>
<br>

サンプルを用意しています。ファイル名を"servo.txt"に変更してご使用ください。<br>
<br>


## 必要なもの
### 本体<br>
いずれかを用意してください。<br>
・M5Stack Core2 for AWS<br>
・M5Stack Core2 v1.0<br>

<b>M5Stack Core2 v1.1 は、対応していません。</b><br>
　（SD_Updater の menu.bin が非対応であるため）<br>
<br>

### サーボ
サーボが無くても顔だけの動作も可能ですが、あると楽しいです。<br>
・SG90　または互換<br>
・サーボポートは、PortAまたは、PortC のどちらも対応。<br>
<br>

### SDカード
SDルートに設定ファイル"servo.txt"が必要です。<br>
<br>


## 最新BINの取得
コンパイル済みの最新BINファイルは、下記のリポジトリから取得できます。
- [BinsPack-for-StackChan-Core2](https://github.com/NoRi-230401/BinsPack-for-StackChan-Core2)<br>
<br>


## SD-Updaterについて
tobozoさん開発。SDに複数のBINファイルを入れて、ソフトを切替えて使用できるようになります。<br>

 https://github.com/tobozo/M5Stack-SD-Updater<br><br>


タカオさん、2023/7/29 ｽﾀｯｸﾁｬﾝ お誕生日会 2023のLTで、M5Stack-SD-Updaterの概要を説明した時のスライド<br>
https://speakerdeck.com/mongonta0716/sutatukutiyandefu-shu-apuriwoqie-riti-erutekunituku

<br><br>


## 基のリポジトリ
- [AI-StackChan2　(robo8080さん)](https://github.com/robo8080/AI_StackChan2)<br>
<br>
<br><br>

以下、AI-StackChan2　(robo8080さん)の説明を掲載しています。

-----



# AI_StackChan2
AIｽﾀｯｸﾁｬﾝ2です。
<br><br>

![画像1](images/image1.png)<br><br>

AIｽﾀｯｸﾁｬﾝ2の特徴<br>

* 音声合成にWeb版 VOICEVOXを使います。
* 音声認識に"Google Cloud STT"か"OpenAI Whisper"のどちらかを選択できます。
<br>

Google Cloud STTは、”MhageGH”さんの [esp32_CloudSpeech](https://github.com/MhageGH/esp32_CloudSpeech/ "Title") を参考にさせて頂きました。ありがとうございました。<br>
"OpenAI Whisper"が使えるようにするにあたって、多大なご助言を頂いた”イナバ”さん、”kobatan”さんに感謝致します。<br>
ウェイクワードには、”MechaUma”さんの[SimpleVox](https://github.com/MechaUma/SimpleVox/ "Title")ライブラリを使わせていただきました。

---


### M5GoBottom版ｽﾀｯｸﾁｬﾝ本体を作るのに必要な物、及び作り方 ###
こちらを参照してください。<br>
* [ｽﾀｯｸﾁｬﾝ M5GoBottom版組み立てキット](https://raspberrypi.mongonta.com/about-products-stackchan-m5gobottom-version/ "Title")<br>

### プログラムをビルドするのに必要な物 ###
* [M5Stack Core2](http://www.m5stack.com/ "Title")<br>
* VSCode<br>
* PlatformIO<br>

使用しているライブラリ等は"platformio.ini"を参照してください。<br>

~~【5/31の時点ではM5Unifiedの不具合の為、CoreS3では動きません。】~~<br>

---

### サーボモーターを使用するGPIO番号の設定 ###
* main.cppの46行目付近、サーボモーターを使用するGPIO番号を設定してください。


### 使い方 ###

こちらを参照してください。<br>

* [AI_StackChan2_README](https://github.com/robo8080/AI_StackChan2_README/ "Title")<br>
<br>
<br>
<br>
