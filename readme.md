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
## 1 Viewは何をするところでしょうか。簡潔に説明してみてください。  

Controllerの指示によってアクセスしてきたユーザーのブラウザに表示するデータを生成する。  

## 2 プログラマーがhtmlを書かずにPHPなどのプログラミング言語やフレームワークを使う必要があるのはどういった理由でしょうか。  

動的なwebページを作成するため。  

## 3 【応用】 前々章でAdmin/ProfileControllerのadd Action, edit Action に次のように記述しました。add Action と edit Action を描画するには、それぞれどこのディレクトリに何というbladeファイルを設置すれば良いでしょうか。  

add Action  
`resources/views/admin/profile/create/create.blade.php`  
edit Action  
`resources/views/admin/profile/edit/edit.blade.php`  

## [メモ]
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

