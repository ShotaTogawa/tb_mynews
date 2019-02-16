#PHP/Laravel 09
##[メモ]
・コントローラーの生成コマンド
ex) php artisan make:controller Admin/NewsController


##[課題]
###1.ControllerとRoutingについてわからないことを書き出してメンターに質問してみましょう。
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

###2.Controllerの役割について、説明してください。
requestをroutingによって、該当するコントローラがModelがブラウザに表示するデータを生成し、Viewにデータを連携するよう指示を出す。
Modelを返さなければ、そのままViewに連携される。
ActionはControllerの持つ機能。Controller内に実装したメソッドをさす。
Routingを設定しないとActionが使われることはない。

###3.ControllerとRoutingの役割について、説明してください。
Routingは来たアクセスをControllerの中のActionに渡す。
コンテンツを作りたい場合はControllerにActionを作り、RoutingでそのActionに割り当てれば良い。
