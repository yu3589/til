## slimとは
シンプルなテンプレート言語。閉じタグが不要で、erbよりも見た目がスッキリして可読性が上がる。

- クラス、idの指定
```slim
/ slim
/ クラスは　.
dev.content
  p.title タイトル
/ idは #
dev#content
  p#title タイトル
```
 ↓ htmlでは下記のように表示される
```html
<!-- html -->
<dev class="content">
  <p class="title">タイトル</hoge>
</dev>
<dev id="content">
  <p id="title">タイトル</hoge>
</dev>
```
---
- if文
```slim
/ slim
/ if文は - で囲む。endを書く必要がない
- unless current_user
  li 新規登録
- else
  li ログイン
```
 ↓ htmlでは下記のように表示される
```html
<!-- html -->
<% unless current_user %>
  <li>新規登録</li>
<% else %>
  <li>ログイン</li>
<% end %>
```
---
- 出力
```slim
/ 出力は = 
- sum = 5 + 5
= sum
/ => 10 が出力される
```
 ↓ htmlでは下記のように表示される
```html
<!-- html -->
<% sum = 5 + 5 %>
<%= sum %>
```
参考：https://qiita.com/ngron/items/c03e68642c2ab77e7283
