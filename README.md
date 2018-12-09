# motoko

`motoko` → `素子` → `element` → `要素` 自体にスタイルを適用する軽量 CSS フレームワーク。  
何でも良いから適当なスタイルを手っ取り早く適用したい人向け。  

## Usage

motoko.css ファイルを読み込むだけ。

```
<link href="./motoko.css" rel="stylesheet">
```

`class="motoko"` と記述したタグ内部の全要素に motoko のスタイルが適用される。

```
<!DOCTYPE html>
<html class="motoko">
  <head>
    <meta charset="UTF-8">
    <title>motoko</title>
    <link href="./motoko.css" rel="stylesheet">
```

## Etc

ファイル参照ボタンには下記スクリプトが必要になる。

```
window.motoko = window.motoko || {

  onChangeFile: (self) => {
    self.parentNode.parentNode.querySelector("p").innerHTML = self.value.match(/([^\/\\]+)$/)[1];
  }

};

window.document.addEventListener("DOMContentLoaded", () => {
  window.document.querySelectorAll(".motoko-file input[type='file']").forEach((fileNode) => {
    fileNode.addEventListener("change", (event) => {
      window.motoko.onChangeFile(event.target);
    });
  });
});
```
