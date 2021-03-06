# デザインパターンを学ぶ上での心得
* デザインパターンの目的の1つは、**プログラムを再利用可能にする**（変更しやすくする）こと。具体的には以下を意識してみる
  * **どの部分が変わりやすいのか**
  * **変わったとき、どこに修正が必要となるのか**
  * **逆に、修正が不要なのはどこか**
* どのクラスやどのインターフェースが、**どういった役割なのか** を考える

# 補足
* 抽象クラスやインターフェースの使用を心がけたプログラムにする
  * 具体的な実装クラスだけで解決しようとする（全メソッドを全部実装クラスに書く）と、結合が強くなり **再利用しづらくなる**

# Iteratorパターン
参考：https://qiita.com/tanakahisateru/items/0a2c3cd2c3af1459902f

## まずはお作法の考え方

### 変わりやすいのは？
サンプルでいうと、本棚（BookShelf）
* 本を詰め込む箱の実装（データ構造。配列なのか、コレクション（例えばArrayList）なのか、、）が変わりやすい

### 変わらないのは？
サンプルでいうと、whileループ
* その（データ構造を変えた）とき変わりにくいのは、例えばループを回したりする処理

## 使いどころは？


## ほか補足
* *なんかわざわざ配列のループっぽいことを面倒くさくしてる、、* と思ってたが、この考え方自体が誤り。Iteratorという上位概念があって、forループは配列を回すための手段の1つにすぎない！
* データ構造によらず、（例えば数え上げなどの）操作が可能になる
* あと、Iteratorは（単純に頭からのカウントアップじゃなく）逆さから数えたりできる


# Adapterパターン

## まずはお作法の考え方

### 変わりやすいのは？
サンプルでいうと **Adaptee役** であるBanner
* APIをイメージするとよい。（v1→v2→v3....）

### 変わらないのは？
サンプルでいうと、 **Target役である** Printインターフェース（もしくは抽象クラス）  
加えて、**Client役** のMainクラス


## 使いどころは？
`うーん、ぱっと出てこないや、、`

## ほか補足
* **使用するのはあくまでTarget役のメソッド** である！
  * Adapterはあくまで実装or継承しているだけ！という理解
