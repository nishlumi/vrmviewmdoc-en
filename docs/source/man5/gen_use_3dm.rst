########################
3Dモデルの使い方
########################

.. contents::


3Dモデルを開く・操作する
============================

　本アプリの基本的な用途です。VRMやobjやFBXなどの一般的な3Dモデルを読み込み、動かしていきます。

　基本的な機能は :doc:`../man2/operation_initial` をご覧ください。そこでは次の機能を知ることができます。

    * オブジェクトの開き方
    * 一度開いたオブジェクトの履歴の使い方
    * オブジェクトの選択の仕方
    * (グローバル)位置や回転・倍率の使い方
    * etc...

　オブジェクトのプロパティ自体について知りたい場合は :doc:`../man2/property` をご覧ください。

　オブジェクトの操作や補足事項を知りたい場合は :doc:`../man2/operation` をご覧ください。

.. hint::
    　3Dモデルファイルを開く際はあらかじめ設定の ``メモリの使用率`` で必要と思われるサイズに増やしておくことをオススメします。

    ただし、ご利用中の端末のメモリが少ない場合は本アプリで多く確保しすぎると動作が不安定になる可能性があります。どのくらいメモリを確保すべきかはご自身で判断してください。

|

.. _general_use_3dposemot:

3Dモデルにポーズ・アニメーションさせる
=========================================

　本アプリのメインの用途です。UnityエディタやBlender等の高機能すぎるアプリを使わずに、手軽にキーフレーム方式のアニメーション作成を行うことができます。

基本的な説明
     :doc:`../man4/about` や :doc:`../man4/specification` をご覧ください。

VRMの操作について
     :doc:`../man2/operation_vrm` にて詳しく説明しています。なお、ポーズについてはキーフレームに登録しなくても動かしただけですぐに反映されています。

アニメーションの登録について
     `キーフレームに登録する・更新する <../man4/animation_register.html#index-2>`_ をご覧ください。

.. note::
    　本アプリのボーンの可動システムは **IK方式** が基本です。ボーンの回転のみで動かす **FK方式** ではないため、手足や腰の位置がVRMの身長・体格によって若干の差が生じます。

    　身長差のあるポーズやモーションファイルを読み込んだ時はその身長差を自動的に計算して解決しておりますが完璧ではありません。ご了承下さい。

    　なお、FK方式は将来的に対応する予定です。

|

.. index::
    VRMを動かす色んな方法

VRMを動かす色んな方法
--------------------------------

    　本アプリではVRMを動かすのに次の方法を用意しています。それぞれ特徴やポーズを取らせるための精度が異なります。

    IKマーカー
        基本の操作方法。IKマーカーを動かすことにより、その位置めがけてVRMの各部位が移動・回転してその通りにポーズを取ります。高精度。

        詳しくは :ref:`inputikasmarker` をご覧ください。

        .. image:: ../img/operation_vrm_6.png
            :align: center
            :width: 400

        |

    MediaPipeのAIによるポーズ認識
        GoogleのMediaPipeのPose機能により、ウェブカメラで映した対象からポーズを検出し、それに近いポーズを取得します。低精度。

        詳しくは :doc:`../man3/posing_mediapipe` をご覧ください。

        .. image:: ../man3/posing_c.png
            :align: center
            :width: 400

        |

        　MediaPipeが返すボーンの位置・回転情報はUnityのものとも本アプリのIKのものとも異なるため、変換が必要になります。そのため低精度とさせていただきます。あくまでモデルの映像・画像に近いポーズを取らせ、後は手動で調整する・・・という流れを許容していただけるなら有効にご活用いただけます。

        ※精度については今後も調整を続けていきます。

    スプレッドシートで直接指定
        IKマーカーの位置や回転をスプレッドシート形式で各セルに入力し、そのとおりにポーズを取ります。高精度。

        詳しくは :ref:`inputikasnumber` をご覧ください。

        .. image:: ../img/screen_ikmarker.png
            :align: center
            :width: 400

        |

        　本来はIKマーカーを動かしてボーンを移動・回転させるのを、スプレッドシートで直接移動量・回転量を小数点付きで入力して指定できます。コピーしてExcelやGoogleスプレッドシートに保存することもできます。もちろん、その逆で **本アプリのスプレッドシートに貼り付ける** こともできます。

        その他、ポーズの微修正にも活用できるでしょう。

VRMのポーズを反転する
-----------------------------

　スプレッドシートのみの機能ですが、VRMのポーズを反転することができます。

.. |btnbonetranapply| image:: ../img/operation_vrm_l.png
.. |btnbonetranmirror| image:: ../img/operation_vrm_n.png

1. VRMのプロパティの ``IK、全身`` パネルにある ``IK位置の一括変更`` をクリックし、IKマーカーの一括変更ウィンドウを表示します。
2. 上部のツールバーにある |btnbonetranmirror| をクリックします。
3. |btnbonetranapply| ポーズを適用をクリックします。

　すると現在のポーズが反転します。動きとしてはスプレッドシートのセルを入れ替えているだけなので、その際に手入力すれば反転しつつ一部だけ変えるということも可能です。


|

.. index:: 
    IKマーカーの便利な使い方
    IKマーカーを複数同時に動かす
    IKマーカーの移動や回転を元に戻す

IKマーカーの便利な使い方
------------------------------

　IKマーカーはただ動かすだけではありません。次のように便利に使うことができます。詳しくは :ref:`specialoperation_vrm` をご覧ください。

複数同時に動かす
    　同時にIKマーカーが複数存在するVRMだけですが、IKマーカーを複数選択して動かすことができます。

    .. image:: img/spcl_06.png
        :align: center

    ``Ctrlキー`` を押しながらIKマーカーを一つ以上クリックしてください。すると、IKマーカーが複数赤くなります。その状態で移動したり回転すると、同時に動かすことができます。

    ただし、当たり判定が存在するので適時カメラをズームインするなどしてみやすさを調整して操作してください。

IKマーカーの移動を取り消す
    　 ``Shiftキー`` + ``Z`` でIKマーカーの直前の移動・回転を元に戻すことが出来ます。

    　 ``Shiftキー`` + ``Y`` でその戻しをやり直すことができます。

    .. caution::
        通常のアプリの Ctrl + Z のように Ctrlキーではないのでご注意ください。


|

.. index::
    ポーズやモーションを扱う

ポーズやモーションを扱う
============================

　ここでは主にポーズやモーション自体の扱い方について説明をまとめていきます。

本アプリでできることと、外部への出力ファイルは次のように対応しています。

.. csv-table::
    :header-rows: 1
    :align: center

    動作, 対象, 出力ファイル, 参照ページ
    ポーズ, VRM, ``.vvmpose`` , :doc:`../man3/posing`
    モーション, すべてのオブジェクト, ``.vvmmot`` , :ref:`savemotionfile`
    プロジェクト, すべてのオブジェクト＋現在のアニメーションの設定, ``.vvmproj`` , :ref:`saveproject` 

　 **ポーズとモーション** は実際のオブジェクトに依存しないため、別のオブジェクトを割り当てているロールに読み込んでそれを再現することができます。ポーズファイル・モーションファイルを配布することで、他のユーザーにも使っていただくことが可能です。

.. warning::
    VRMの場合、身長差が極端にあると許容できないズレが生じることがあります。配布する際は参考情報として元のVRMの身長を知らせるとよいでしょう。

    ※MMDのようにボーンの回転角度を直接指定する方式ではなく、IK方式のため身長・体格の誤差吸収が完全ではありません。ご了承下さい。

　 **プロジェクト** はもともと開いていたオブジェクトファイルも開こうとする関係上、他ユーザーへの配布には適しません。とはいえ、 `ロールにキャストを割り当てる <../man4/animation_proper.html#index-4>`_  操作をすることにより、別のオブジェクトでもモーションを可能な限り再現させることができます。

　もし配布を考えている場合、一度履歴を削除してからプロジェクトファイルを開いて、ロールにキャストを割り当てる操作を試してみるなどして、事前に確認することをオススメします。

|

タイムラインとオブジェクトを紐づける
=====================================

　タイムラインやオブジェクトの関係について詳しくは、上記と同じく :doc:`../man4/specification` を参照してください。

　本アプリでは一度ポーズやモーションをさせたロール（タイムライン）に対し、後から実際のオブジェクトだけ差し替えて別のオブジェクトで同じポーズやモーションをさせて楽しむことができます。

:ref:`settingcast2role`


|

.. index::
    アニメーションのFPSを調整する
    タイムラインごと・キーフレームごとの調整

アニメーションのFPSを調整する
==================================

プロジェクト単位での調整
    　アニメーションプロジェクトごとにFPSを調整することができます。

    　詳しくは :ref:`setfpsframe` をご覧ください。また、FPSを変更するのではなく、キーフレーム登録時にデフォルトでセットされる間隔(duration)の基準値だけを変更したい場合は :ref:`setdefaultduration` をご覧ください。

タイムラインごと・キーフレームごとの調整
    | 　プロジェクトで決められたFPSと間隔(duration)に従う場合、キーフレームごとの間隔(duration)は基本的にはフレーム間を目的に沿って適切に離して登録します。すると自動的に間隔(duration)が計算されてセットされます。
    | 　プロジェクトの間隔(duration)に従うと、膨大なフレームが必要になる可能性もあります。それが労力的に問題なければ構いません。

    .. image:: ../man4/img/register_7.png
        :align: center

    |

    　少ないフレームで自在にモーションを作りたい場合、キーフレームの設定で間隔(duration)を直接編集するとよいでしょう。
    
    .. image:: ../man5/img/spcl_09.png
        :align: center
    
    |

    詳しくは :ref:`modifyeachduration` をご覧ください。