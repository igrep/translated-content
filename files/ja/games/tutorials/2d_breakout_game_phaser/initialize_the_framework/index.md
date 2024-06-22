---
title: フレームワークの初期化
slug: Games/Tutorials/2D_breakout_game_Phaser/Initialize_the_framework
l10n:
  sourceCommit: 56db19e6b8d19932c1b6150bc42e752e12a2b21f
---

{{GamesSidebar}}

{{PreviousNext("Games/Workflows/2D_Breakout_game_Phaser", "Games/Workflows/2D_Breakout_game_Phaser/Scaling")}}

こちらは、[Gamedev Phaser](/ja/docs/Games/Tutorials/2D_breakout_game_Phaser) の使い方を学ぶための 16 のチュートリアルの一つ目です。このチュートリアルを完了した後は、このセクションのソースコードを [Gamedev-Phaser-Content-Kit/demos/lesson01.html](https://github.com/end3r/Gamedev-Phaser-Content-Kit/blob/gh-pages/demos/lesson01.html)でチェックしてみてください。

ゲームの機能を書き始める前に、ゲームをレンダリングするための基本的な構造を作成する必要があります。これには HTMLを使用しましょう。Phaser フレームワークが必要な {{htmlelement("canvas")}} 要素を生成してくれます。

## ゲームの HTML

HTML ドキュメントの構造は非常にシンプルです。ゲームの全体はフレームワークが生成した {{htmlelement("canvas")}} 要素上にレンダリングされます。お好きなテキストエディタを使用して新しい HTML ドキュメントを作って `index.html` として保存し、適切な場所に以下のコードを追加しましょう:

```html
<!doctype html>
<html lang="ja">
  <head>
    <meta charset="utf-8" />
    <title>Gamedev Phaser Workshop - lesson 01: フレームワークの初期化</title>
    <style>
      * {
        padding: 0;
        margin: 0;
      }
    </style>
    <script src="js/phaser.min.js"></script>
  </head>
  <body>
    <script>
      const game = new Phaser.Game(480, 320, Phaser.CANVAS, null, {
        preload,
        create,
        update,
      });
      function preload() {}
      function create() {}
      function update() {}
    </script>
  </body>
</html>
```

## Downloading the Phaser code

Next, we need to go through the process of downloading the Phaser source code and applying it to our HTML document. This tutorial uses Phaser V2 — it won't work with the current version on Phaser (V3). The V2 library is still available on the Phaser download page, below the links for the V3 download.

1. Go to the [Phaser download page](https://phaser.io/download/stable).
2. Choose an option that suits you best — we recommend the _min.js_ option as it keeps the source code smaller, and you are unlikely to go through the source code anyway. **Please make sure to use Phaser version 2 as that's what this tutorial was written for.**
3. Save the Phaser code inside a `/js` directory in the same location as your `index.html` file.
4. Update the `src` value of the first {{htmlelement("script")}} element as shown above.

## Walking through what we have so far

At this point we have a `charset` defined, {{htmlelement("title")}} and some basic CSS in the header to reset the default `margin` and `padding`. We also have a {{htmlelement("script")}} element to apply the Phaser source code to the page. The body contains a second {{htmlelement("script")}} element, where we will write the JavaScript code to render the game and control it.

The {{htmlelement("canvas")}} element is generated automatically by the framework. We are initializing it by creating a new `Phaser.Game` object and assigning it to the game variable. The parameters are:

- The width and height to set the {{htmlelement("canvas")}} to.
- The rendering method. The three options are `AUTO`, `CANVAS` and `WEBGL`. We can set one of the latter two explicitly or use `AUTO` to let Phaser decide which one to use. It usually uses WebGL if available in the browser, falling back to Canvas 2D if not.
- The `id` of the {{htmlelement("canvas")}} to use for rendering if one already exists on the page (we've specified null because we want Phaser to create its own.)
- The names to use for Phaser's three key functions that load and start the game, and update the game loop on every frame; we will use the same names to keep it clean.

  - `preload` takes care of preloading the assets
  - `create` is executed once when everything is loaded and ready
  - `update` is executed on every frame.

## Compare your code

Here's the full source code of the first lesson, running live in a JSFiddle:

{{JSFiddleEmbed("https://jsfiddle.net/end3r/h6cwzv2b/","","400")}}

## Next steps

Now we've set up the basic HTML and learned a bit about Phaser initialization, let's continue to the second lesson and learn about [scaling](/en-US/docs/Games/Tutorials/2D_breakout_game_Phaser/Scaling).

{{PreviousNext("Games/Workflows/2D_Breakout_game_Phaser", "Games/Workflows/2D_Breakout_game_Phaser/Scaling")}}
