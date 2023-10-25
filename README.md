# java　インスタンスの5大基本操作
## Objectクラスに備わる基本機能
### javaにおける全てのクラスは、継承関係を親へ辿っていくと「java.lang.Object」のクラスに行き着く。

## 多くのインスタンスに共通する5つの基本操作
### メソッド、操作の内容、関連するクラスの順で記載
### ◯toString()、文字列表現を得る、Object
### ◯equals()、等価判定を行う、Object
### ◯hashCode()、ハッシュ値を得る、Object
### ◯compareTo()、大小関係を判定する、Comparable
### ◯clone()、複製する、Object・Cloneable
### ※toString()、equals()、hashCode()の3つは特に重要なメソッド

### toString()のオーバーライド
#### 新たなクラスを開発したら、toString()をオーバーライドしておくことで開発者が意図した文字列表現を渡すことができる。行わなければ意図したものとは結果が表示される。
