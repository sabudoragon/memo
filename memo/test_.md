復習

リポジトリ→プロジェクトの履歴を保存する場所  
コミット→変更リれr気を保存する捜査。又は履歴自体。  
自分のＰＣ内にあるリポジトリを**ローカルリポジトリ**という。  
GitHub等にあるリポジトリを**リモートリポジトリ**という。  
# ローカルリポジトリの操作
- ファイルを変更
- コミット対象を選ぶ
    - **ステージング**
- コミット
    - **コミットメッセージ**　○○を修正しました←これのこと
# ローカルリポジトリとリモートリポジトリの連携
- リモートへ共有する
    - プッシュ
プッシュとは反対にリモートリポジトリの履歴をローカルリポジトリに反映するためには**プル**という操作をする

## Flutterとは
Flutterは**Google**がオープンソースの**フレームワーク**の一つ。  
一つのソースで複数のプラットフォームに対応することができる。
## Dartとは
Flutterによる開発で使用されるプログラミング言語。  
Flutter同様にGoogleが中心なって開発された言語。
### 順次処理
上から順に
### 繰り返し処理
同じ処理を繰り返えし処理
### 分岐処理
条件によって実行する処理が変わる処理
### 型と値
整数型 int  
小数点型 double  
文字列型 String  
真偽型 bool  
### 演算
AをBで割ったあまり　A%B  
AをBで割った整数値  A~/B

テキスト+テキスト　足算  
テキスト*整数  　　引算

```
Flutter doctor→確認

Flutter create 名前→プロジェクトを作成するコマンド
```

引数が多くなればなるほど、どの引数がどの役割かわかりづらくなる。  
呼び出し時に引数が足りなければエラーとなる。  
一つの引数には一つの値を渡し、一つの関数からは一つの値が返ってくる。  
それぞれの処理で、どんな値を渡すのか、どんな値が返ってくるかを意識することが重要。  
部品の中に部品を入れていくマトリョシカのような構造でアプリケーション開発

**部品：ウィジェット**  
**構造：ウィジェットツリー**  

ステート（状態）を持たない  
StatelessWidget

ステート（状態）を持つ  
StatefullWidget

構造となるウィジェットはmain関数から呼ばれる  

オリジナルウィジェットを作るときは**extends**を使う  
**@overrid**を書く  
buildメソッド→をジェットを生成するときに呼び出されるメソッド

onpress→押されたときに呼ばれるメソッドを書く

setState→ステートの更新があったことを知らせて画面を更新する
文字サイズ
フォント
文字の太さ

色指定
```
Color(0x00000000)
```
ARGB2桁ずつ使う  
Color.fromARGBを使うことで10進数で書ける
```
Color.fromARGB(255, 255, 3, 4)
```

Center  
child指定したWidgetを上下中央揃えで表示する

Container  
Centerよりも、より細かく一の寮生をする場合に使用する  
Edelnsets:周囲の余白幅を設定するためのクラス  
Alignment:配置場所を設定するためのクラス

Column:複数のウィジェットを縦に並べて表示する
```
Column(
    mainAxisAlignment: MainAlignment.start,
    mainAxisSize: MainAxisSize.max,
    crossAxisAlignment: CrossAxisAlignment.center,
    children: <Widget>[
        Text(略),
        Text(略),
        Text(略)
    ]
),
```
上下の位置：mainAxixAlignment: MainAxisAlignment.start,  
左右の位置：corssAxixAlignment: CrossAxixAlignment.center,  
Rowでは左右の位置になることに注意しましょう  
```
TextButton(
    onPressed: buttonPressed,
    child: Padding(
        padding: EdgeInsets.all(10.0),
        child: Text(
            "Puch me!",
            sytle: TextStyle(略)
        )
    )
)
```
onPressed ボタンが押されたときに実行されるメソッド  
child ボタン内に表示するウィジェット  
カスケード記法　式の値をもとにオブジェクトにしたまま操作を行う記法  
               同一のオブジェクトに対して複数の操作を行うことができる
```
janken..shuffle()
```

TextField  
自由に文字を入力させたいとき  

ChecBox Switch   
要素に該当するかどうかチェックさせたいとき

Radio DropdpwnButton PopupMenuButton  
複数の要素から一つだけ選ばせたいとき

Slider  
特定の値の範囲で数値を入力させたいとき

# TextField
文字を入力できるだけ  
入力された値を保持しているわけではない  
値の操作にはControllerが必要 _controller  
値が変更されるたびに呼ばれる**onChange**というイベントもある

3項演算子
```
void main() {
    int a = 10;

    print(a < 10 ? "ok" : "ng");
}
```

```
showDialog(
    context: context,
    builder: (BuildContext context) => Alertdialog(
        title: Text("Hello!"),
        content: Text("This is sample.")
    )
)
```
AliertDialog:アラートを表示することのできるdialog
```
AlertDialog(
    title: ウィジェット,
    content: ウィジェット,
)
```

## TabBarの基本形
```
TabBar(
    controller:<<TabController>>,
    tabs: [Tabのリスト],
),
```

## Sliderの基本形
```
slider(
    onChanged: 関数,
    min:<<double>>,
    max:<<double>>,
    divisions:<<int>>,
    value:<<double>>,
),
```
onChange:変更時のイベント処理。ドラッグ中、値が変わるたびに呼び出される。  
min:最小値  
max:最大値  
divisions:分割数。例えばmin:0,max:10でdivisions:10ならば、1ずつ値が選択される。  
　　　　　　省略すると実数のまま滑らかに値が変化していく。  
value:現在選択されている値  

SimpleDialogについて

```
SinpleDialog(
    title: ウィジェット,
    childern: [ウィジェットのリスト],
)
```
titleには、タイトルのテキストなどを設定。通常はtextを指定する。childrenには選択肢として表示する項目のリストを用意。  

SimpleDialogOptionについて  
```
SinoleDialogOption(
    child:ウィジェット,
    onPressed:処理,
)
```
childには、項目内に表示するウィジェットを指定。テキストを表示するだけならtextのみ。  

ElevatedButtonについて  
TextButtonと同じような働きをする。これはbuttonが少し立体的に表示される。  

IconButtonについて
```
IconButton(
    icon: const Icont(Icons.insert_emoticon),
    iconSize: 100.0,
    color: Colors.red,
    onPressed:buttonPressed,
)
```
icon:表示するアイコン。iconインスタンスとして用意する  
iconSize:アイコンサイズ。double値で指定  
color:アイコンの色  
onPressed:クリックしたときに実行するメソッド

FloatingActionButtonについて
```
FloatingActionButton(
    child: Icon(Icons.android),
    onPressed: buttonPressed
),
```
Scaffoldにこれを設定することで、画面右下に自動的にボタンが追加表示されるようになる。