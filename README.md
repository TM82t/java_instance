# java インスタンス
## javaのインスタンスについてまとめていく
### インスタンスの生成
クラスからインスタンスを生成するには「new クラス名()」。  
インスタンスは変数に代入して用いる。  
変数にインスタンスを代入するには「クラス型 変数名 = new クラス名()」。  
  
### インスタンスの情報と振る舞い
インスタンスの情報にあたるものを「インスタンスフィールド」、振る舞いにあたるものを「インスタンスメソッド」と呼ぶ。  
インスタンスメソッドは「public 戻り値の型 メソッド名()」と定義。  
インスタンスメソッドはインスタンス（を代入した変数）に対して呼び出す。(「インスタンス名.メソッド名()」)  
インスタンスフィールドには「インスタンス名.フィールド名」と、インスタンスに対してドット（.）を用いてアクセスする。  
ドットを用いること以外、変数と扱いはあまり変わらず、値の取得とセット（代入）が可能。  
  
### this
メソッド内でインスタンスフィールドにアクセスするためには「this」という特殊な変数を用いる。  
thisはクラス内のメソッドの定義の中でのみ使用可能。  
メソッドが呼ばれた時に、そのメソッドを呼び出しているインスタンスに置き換えれる。  
例
```
class Person {
  public String name;

  public void hello() {
    System.out.println("こんにちは、私は" + this.name + "です");
  }
}
```
  
### コンストラクタ
クラスには、コンストラクタというものがある。  
コンストラクタとは、newを使ってインスタンスを生成した後に自動で呼び出される特別なメソッド。  
コンストラクタは特別なメソッドのため、定義方法が決まっている。  
①コンストラクタ名はクラス名と同じにする  
②戻り値を書いてはいけない（voidも書かない）  
この2つの決まりさえ守れば、コンストラクタの完成。  
例  
Main.java  
```
class Main {
  public static void main(String[] args) {
    Person person1 = new Person("Kate Jones");
    person1.hello();

    Person person2 = new Person("John Christopher Smith");
    person2.hello();
  }
}
```
  
Person.java
```
class Person {
  public String name;

  Person(String name) {
    System.out.println("インスタンスが生成されました");
    this.name = name;
    
  }

  public void hello() {
    System.out.println("こんにちは、私は" + this.name + "です");
  }
}
```
  
・より多くの情報を表示させる例  
Main.java  
```
class Main {
  public static void main(String[] args) {
    Person person1 = new Person("Kate", "Jones", 27, 1.6, 50.0);
    
    System.out.println(person1.firstName);
    System.out.println(person1.lastName);
    System.out.println(person1.age);
    System.out.println(person1.height);
    System.out.println(person1.weight);
  }
}
```
  
Person.java  
```
class Person {
 public String firstName;
 public String lastName;
 public int age;
 public double height;
 public double weight;

  Person(String firstName, String lastName, int age, double height, double weight) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
    this.height = height;
    this.weight = weight;
  }
```
  
  
### java　インスタンスの5大基本操作
#### Objectクラスに備わる基本機能  
javaにおける全てのクラスは、継承関係を親へ辿っていくと「java.lang.Object」のクラスに行き着く。
  
### 多くのインスタンスに共通する5つの基本操作
#### メソッド、操作の内容、関連するクラスの順で記載
#### ◯toString()、文字列表現を得る、Object
#### ◯equals()、等価判定を行う、Object
#### ◯hashCode()、ハッシュ値を得る、Object
#### ◯compareTo()、大小関係を判定する、Comparable
#### ◯clone()、複製する、Object・Cloneable
#### ※toString()、equals()、hashCode()の3つは特に重要なメソッド
  
### toString()のオーバーライド
新たなクラスを開発したら、toString()をオーバーライドしておくことで開発者が意図した文字列表現を渡すことができる。  
行わなければ意図したものとは結果が表示される。  
  
### equel()のオーバーライド
equel()のオーバーライドを怠ると何かのきっかけで原因特定が困難な不具合が生じることがある。  
クラスを作成したら必ずequel()をオーバーライドする。  
  
### clone()のオーバーライド
Objectクラスで定義しているclone()はprotectedで宣言されているため、外部から呼び出せない。  
オーバーライドの際はpublicでオーバーライドし、外部から呼び出せるようにしておく。  
インスタンスの複製方法にはインスタンスの参照先を考慮した深いコピーと考慮しない浅いコピーがある。  
インスタンスを完全に複製するには深いコピーが必要。  


