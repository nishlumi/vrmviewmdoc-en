###########################################
VR/ARの基本
###########################################

.. contents::

.. index:: 
    確認済みの環境・機能(VR/AR)

確認済みの環境・機能
######################################

　本アプリでのVR/ARは、通常のアプリ画面と切り替えて使用します。常にVR/AR状態ではありませんので、VR機器でも通常画面を使用することもできます。

* Meta Questのブラウザ(VR/AR)
* PICO のブラウザ(VR/AR)
* Quest Linkにて接続したPC上のブラウザ(PWA含む)(VR)

.. hint::
    * Quest Linkの接続は、Air Linkよりも有線接続の方をお勧めします。Air LinkでもVR機器のブラウザより遥かに高速な動作を期待できますが、実際にモーションを動かすとチラつきが発生します。
    * ブラウザのページの倍率を **80%程度** に縮小すると、通常画面での利用もしやすくなります。（Oculus Linkによる利用では解像度が高いため、ページの倍率は特に必要ないと思われます）


.. index::
    VR/ARの制限事項
    VR/AR時の別ウィンドウ

制限事項
######################################

* Quest Linkにて接続したPC上の各OS版（Electron版）ではVR/AR両方とも利用できません。
* 本アプリはWebGLビルドのためブラウザが利用できる各端末の性能に大きく依存します。各OSネイティブアプリよりも制限があります。また、通常画面とVR/AR画面切り替えもある程度負荷があるため、プロジェクト・モーション・ポーズいずれかのファイル形式で **こまめに保存すること** をお勧めします。
* CameraオブジェクトはVR/AR空間では再生できません。OtherObjectのレンダーテクスチャ機能と組み合わせて使えばVR/AR空間でも別のカメラからの映像を見ることができます。
* SystemEffectはVR/AR空間には反映されません。


別ウィンドウを開く機能について
======================================

キーフレーム設定ウィンドウやポーズ・モーションウィンドウなど、別のウィンドウが開く機能はタブに置き換わります。

Meta Quest3
    タブを別のウィンドウにドラッグして分離できるので、2画面以上で本アプリを使用できるようになるでしょう。

PICO4
    PICO4のブラウザはPWA方式によるウェブアプリのインストールを行うことができます。しかしながらPICO4上でウェブアプリ化した状態で別ウィンドウを開く機能を使うと、ウェブアプリの画面そのものがそのウィンドウに置き換わってしまうことを確認しています。

    どうやらPICOの仕様と思われます。

    PICO4でもブラウザでの使用をお勧めします。


.. index:: VR/AR空間への入り方

VR/AR空間への入り方
######################################

1. リボンバーのホームタブにある ``VR`` または ``AR`` ボタンをクリックします。

.. image:: img/vrar01.png
    :align: center

|

.. caution::
    利用できない環境の場合、それぞれのボタンを押すことは出来ません。


撮影
##################################

VR機器では標準でスクリーンショット・録画機能が備わっているため、それらを使うことを推奨します。

本アプリのスクリーンショット・録画機能も一応利用可能です。