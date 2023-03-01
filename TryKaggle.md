# Kaggleにさわってみた( + AutoML) by Udemy

## Kaggleとは
企業や研究者がデータを投稿し、世界中の統計家やデータ分析家がその最適モデルを競い合う、予測モデリング及び分析手法関連プラットフォームです。 \
[Kaggle - Wikipedia](https://ja.wikipedia.org/wiki/Kaggle) \
[kaggle.com](https://www.kaggle.com/) \
ざっくりすると、一つのデータセットに対して、最も正確なデータ分析モデル構築できるかを競うコンペの場です。 \
コンペの内容によっては賞金が出たりします。 \
Kaggleを頑張るための書籍も複数あります。読んでないので内容は把握していません。 \
[Kaggleに挑む深層学習プログラミングの極意 (KS情報科学専門書)](https://www.amazon.co.jp/Kaggle%E3%81%AB%E6%8C%91%E3%82%80%E6%B7%B1%E5%B1%A4%E5%AD%A6%E7%BF%92%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0%E3%81%AE%E6%A5%B5%E6%84%8F-KS%E6%83%85%E5%A0%B1%E7%A7%91%E5%AD%A6%E5%B0%82%E9%96%80%E6%9B%B8-%E5%B0%8F%E5%B5%9C-%E8%80%95%E5%B9%B3/dp/4065305136/ref=sr_1_1?adgrpid=119548917767&hvadid=626757263471&hvdev=c&hvqmt=e&hvtargid=kwd-606661230664&hydadcr=27299_14609487&jp-ad-ap=0&keywords=kaggle+%E6%9C%AC&qid=1677686833&sr=8-1) \
[The Kaggle Book：データ分析競技 実践ガイド＆精鋭31人インタビュー (impress top gear) ](https://www.amazon.co.jp/Kaggle-Book%EF%BC%9A%E3%83%87%E3%83%BC%E3%82%BF%E5%88%86%E6%9E%90%E7%AB%B6%E6%8A%80-%E5%AE%9F%E8%B7%B5%E3%82%AC%E3%82%A4%E3%83%89%EF%BC%86%E7%B2%BE%E9%8B%AD31%E4%BA%BA%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%93%E3%83%A5%E3%83%BC-impress-gear/dp/4295015954/ref=sr_1_2_sspa?adgrpid=119548917767&hvadid=626757263471&hvdev=c&hvqmt=e&hvtargid=kwd-606661230664&hydadcr=27299_14609487&jp-ad-ap=0&keywords=kaggle+%E6%9C%AC&qid=1677686833&sr=8-2-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUExT1EyNFFERDlIUUxBJmVuY3J5cHRlZElkPUEwNjAwOTY2WTJZUkUwTkRXUVVIJmVuY3J5cHRlZEFkSWQ9QTM1QzdGMzM2Q0VSQjYmd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl) \
[Kaggleで勝つデータ分析の技術](https://www.amazon.co.jp/Kaggle%E3%81%A7%E5%8B%9D%E3%81%A4%E3%83%87%E3%83%BC%E3%82%BF%E5%88%86%E6%9E%90%E3%81%AE%E6%8A%80%E8%A1%93-%E9%96%80%E8%84%87-%E5%A4%A7%E8%BC%94-ebook/dp/B07YTDBC3Z/ref=sr_1_3?adgrpid=119548917767&hvadid=626757263471&hvdev=c&hvqmt=e&hvtargid=kwd-606661230664&hydadcr=27299_14609487&jp-ad-ap=0&keywords=kaggle+%E6%9C%AC&qid=1677686833&sr=8-3) \
コンペに参加しなくてもいろんなデータセットを参照できます。Netflixの過去数年の配信作品とユーザー評価の一覧とか。

## コンペの種類
* タイタニックの乗客データをもとに生存有無を予測する。(Kaggle上のチュートリアル用コンペみたいな感じです。)
* 家屋の特徴情報から住宅の価格を予測する。
* 季節や天候、休暇シーズンなどのデータから自転車のレンタル数を予測する。

## コンペの参加方法
参加したいコンペをサイト上で選択します。 \
コンペに参加して「訓練用データ」、「評価用データ」をダウンロードします。
* 訓練用データ \
「評価したい項目」 + 「評価するための材料」をセットにしたデータです。
* 評価用データ \
「評価するための材料」のみのデータです。

タイタニック号のコンペの場合は、「評価したい項目」が「乗客が生存したかどうか」で、「評価するための材料」が「乗客の性別、乗船料金、年齢、客室種別などなど」です。 \
「訓練用データ」を使って分析モデルを構築した後に、その分析モデルに「評価用データ」を評価させて出た結果をサイトに提出します。 \
提出したデータをサイト側が判定して、どの程度の精度が出せているかを教えてくれます。 \
その精度がコンペ参加者内でのランキングに反映されます。

## AutoMLとは
機械学習の仕組みなどに精通していなくても機械学習の機能を利用できるサービスやツール。 \
機械学習を行うプロセス(問題や仮説の定義、データ収集、データ加工、特徴量設計、機械学習モデルの生成、モデルの運用)の中で、データの加工からモデル設計までを自動化できる。
* 代表的なAutoMLツール：AutoML Table（Google）、Automated ML（Microsoft）、AutoAI（IBM） など

## 実際のモデル構築方法(ソースコード)

```Python
import pandas as pd
from pycaret.classification import *

train_data = pd.read_csv("train.csv")  # 訓練用データ
test_data = pd.read_csv("test.csv") # 評価用データ

# 環境の初期化
clf = setup(data=train_data,
            target="Survived", # 生存有無を評価対象とする
            session_id=123,
            numeric_imputation="mean", # 数値データの欠損は平均値適用
            categorical_imputation="mode") # 分類データの欠損は最頻値適用

best_model = compare_models()  # 全てのモデルを訓練し、評価する
# 最適モデルは勾配ブースティング決定木でした。
#   「勾配降下法 (Gradient)」と「アンサンブル学習 (Boosting)」、「決定木 (Decision Tree)」の3つの手法が組み合わされた機械学習の手法とのことです。

tuned_gbc = tune_model(best_model)  # ハイパーパラメータ？の調整をする
# ハイパーパラメータとは
#   推論や予測の枠組みの中で決定されないパラメータのことを指す。
#   損失関数の正則化項の影響度を表す係数などが該当する。らしい。

final_gbc = finalize_model(tuned_gbc) # 本番用のモデルを作成
# モデル構築時に一部データを使わず確保している。そのデータを含めてモデル化する。
# ほんとはその未使用データでモデルの精度を確認したりする？

plot_model(final_gbc, plot="feature") # これをすると特徴ごとの比重を見せてくれる
# 性別の要素が生存結果に強く影響してました。

save_model(final_gbc,'finalModel') # 学習したモデルは保存して次回に再利用できる

test_pred = predict_model(final_gbc, data=test_data)  # 評価用データに対して予測を行う

# Kaggle提出用に形式を整える(乗客IDと生存結果のみを提出する。)
subm_data = test_pred[["PassengerId", "Label"]]  # 列を抜き出す
subm_data = subm_data.rename(columns={"Label" : "Survived"})  # 列名の変更

# 提出用のcsvファイルを保存
subm_data.to_csv("submission_titanic.csv", index=False)

```
* 補足 \
[Pycaretで使用できる機械学習モデル](
https://qiita.com/Takumi_Fukuda/items/99e60793ac700974cfc4#%E4%BA%88%E6%B8%AC%E3%83%A2%E3%83%87%E3%83%AB%E5%88%86%E6%9E%90%E9%81%B8%E5%AE%9A)
## 使用したライブラリ
* pycaret \
オープンソースの機械学習ライブラリーで、機械学習の一連の作業を自動化する「AutoML」をサポートしています。
* pandas \
データ解析を支援する機能を提供するライブラリである。 特に、数表および 時系列 データを操作するための データ構造 と演算を提供する 。

## 感想
前述のコンペの内容であればPyCaretを使うとほぼコード変更なくある程度評価できてしまう。 \
そのため、そのまま複数のコンペを行っても身になるものがすくなそう。 \
AutoMLは、それを使用せずにモデル構築できるようになったうえで、効率化として使うのがよさそう。

## 参考サイト
[Udemy 【AutoML】自動化された機械学習を学ぼう！ 【PyCaret / Google Colab / Kaggle】](https://www.udemy.com/course/automl-ai/)