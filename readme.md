# PHP/Laravel 09  
## [メモ]  
・コントローラーの生成コマンド  
ex) php artisan make:controller Admin/NewsController


## [課題]  
### 1.ControllerとRoutingについてわからないことを書き出してメンターに質問してみましょう。  
1.課題2と3の認識です。認識違いがあったらご指摘ください。  
2.下記のview('admin.profile.create')とredirect('admin/profile/create)の違いがわかりません。

```php
public function add()
  {
      return view('admin.profile.create');
  }

  public function create()
  {
      return redirect('admin/profile/create');
  }
```

### 2.Controllerの役割について、説明してください。  
requestをroutingによって、該当するコントローラがModelがブラウザに表示するデータを生成し、Viewにデータを連携するよう指示を出す。  
Modelを返さなければ、そのままViewに連携される。  
ActionはControllerの持つ機能。Controller内に実装したメソッドをさす。  
Routingを設定しないとActionが使われることはない。  

### 3.ControllerとRoutingの役割について、説明してください。  
Routingは来たアクセスをControllerの中のActionに渡す。  
コンテンツを作りたい場合はControllerにActionを作り、RoutingでそのActionに割り当てれば良い。  

# PHP/Laravel 10
## [課題]
### 1.URLとControllerやActionを紐付ける機能を何といいますか？

アクセスに応じて対応するControllerのActionを呼び出す仕組み

### 2.あなたが考える、group化をすることのメリットを考えてみてください。

group化することによって可読性があることと、Contorollerが保持しているactionを呼び出すごとにprefixを設定する必要がなくなる。

## [メモ]
・サーバー起動 `php artisan serve`  
・routingファイルの在りか `/routes/wep.php`  

# PHP/Laravel 11  
### 1 Viewは何をするところでしょうか。簡潔に説明してみてください。  

Controllerの指示によってアクセスしてきたユーザーのブラウザに表示するデータを生成する。  

### 2 プログラマーがhtmlを書かずにPHPなどのプログラミング言語やフレームワークを使う必要があるのはどういった理由でしょうか。  

動的なwebページを作成するため。  

### 3 【応用】 前々章でAdmin/ProfileControllerのadd Action, edit Action に次のように記述しました。add Action と edit Action を描画するには、それぞれどこのディレクトリに何というbladeファイルを設置すれば良いでしょうか。  

add Action  
`resources/views/admin/profile/create/create.blade.php`  
edit Action  
`resources/views/admin/profile/edit/edit.blade.php`  

### [メモ]
・viewファイルの生成場所  
`resources/views/`の配下  
・下記はadmin/newsディレクトリ配下のcreate.blade.html というファイルを呼び出す という意味です。  
```php
public function add()
  {
      return view('admin.news.create');
  }
```  
・Viewで出力するhmtlはbladeというテンプレートエンジンを使う。拡張子は`xxxx.blade.php`  

# PHP/Laravel 12  

## [課題]   
### 1.Bladeテンプレートで、埋め込みたい箇所に利用するワードは何だったでしょうか？   
`@yield(引数)` 指定したセッションの内容を表示するために使用する  
extendsで継承できる。　　

## [メモ]  
・asset(‘ファイルパス’)は、publicディレクトリのパスを返す関数。　　
・Webpackは複数に分割されているCSSやJavascriptを一つのファイルにまとめる仕組み。ソースコードを圧縮し、接続速度が早くなります。　　
・`webpack.mix.js`に設定を記載する。　　

# PHP/Laravel 13  

## [課題]  

## [メモ]  
・Authの実装  
```
$ php artisan make:auth
$ php artisan migrate
```  

・middlewareの参考サイト: `https://readouble.com/laravel/5.3/ja/middleware.html`  
・ヘルパ関数: viewで使うための関数の一種  
・route関数: URLを生成したりリダイレクトしたりするための関数。  
・＠csrf: 認証済みのユーザーがリクエストを送信しているのかを確認するために利用する。  参考: `https://readouble.com/laravel/5.6/ja/csrf.html`  
・三項演算子  
`<条件式> ? <真式> : <偽式> ex) a == 1 ? "a=1" : "a is not 1`  
・oldヘルパ関数: セッションにフラッシュデータ（一時的にしか保存されないデータ）として入力されているデータを取得することができる。  
・バリデーション参考: `https://readouble.com/laravel/5.5/ja/validation.html`  
・ブレードテンプレート参考: `https://readouble.com/laravel/5.5/ja/blade.html`  
・ヘルパー参考: `https://readouble.com/laravel/5.5/ja/helpers.html`  
・認証参考: `https://readouble.com/laravel/5.6/ja/authentication.html`  

# PHP/Laravel 14  

## [課題]  

## [メモ]  
・`$errors` は `validate` で弾かれた内容を記憶する配列  
・HTTP: ブラウザとwebアプリケーションが間の通信が発生した際、この通信を行う定められた手順のこと。  
・GET: リクエストは指定したURLの内容を取り出すための要求  
・POST: URLに対して情報を要求するだけでなく、クライアントからさまざまなデータを送信することができる。

# PHP/Laravel 15   

## [課題]  

## [メモ]  
・migrationファイルの作成: `php artisan make:migration create_news_table`  
・カラムの追加: `$table->string('title');`  
・nullの許容: `$table->string('image_path')->nullable();`  
・カラムの追加をしたら`php artisan migrate`を実行する。(rollbackは`php artisan migrate:rollback`)  
・modelの生成: `php artisan make:model News`  
・Debugの方法: `\Debugbar::info(確認したい変数など);`  
・`$request->all();`はformで入力された値を取得することができます  
・basename(): パスではなくファイル名だけ取得するメソッド  
・fill(arr): 配列をカラムに代入するメソッド  
・save(): データベースに保存する　
・アロー演算子(`->`): クラスのメソッドやプロパティにアクセスするための演算子。左辺から右辺を取り出す。　


# PHP/Laravel 19  

## [課題]  

## [メモ]  
・日付操作ライブラリ: `Carbon`  
`->`はクラスから抜き出す「アウトプット」な使い方  
`=>`は配列を仕込む「インプット」な使い方








