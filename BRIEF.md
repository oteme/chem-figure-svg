素の SVG で反応機構の図を書く。描画エンジンは使わない。化学的な正しさはあなたの責任。

確認: scripts/svg2png FILE.svg FILE.png
出力の `ok ...` の PNG を開いて目で確かめる。`error:` は SVG の構文の誤り。

書き方の決まり（教科書の骨格式の体裁）:
- 1つの <svg> に全部を書く。width/height は pt、viewBox を付ける。背景は白、線と文字は黒。
- 結合の長さは 20pt、線幅 1pt。二重結合は平行線2本（間隔 3pt 前後）。
- 原子の文字は sans-serif 10pt 前後。C は骨格の頂点として文字を書かない。O・N・H などは文字で書き、結合は文字の手前で止める。
- 電荷は原子の右上に ⊕ / ⊖（丸で囲んだ記号）。孤立電子対は原子の横に点2つ。
- 反応矢印: 分子の間に水平の直線と塗りつぶした矢じり。条件は矢印の上下に小さな文字で。併記は「+」。
- 巻矢印: 3次ベジェ曲線（<path d="M .. C ..">）と矢じり。始点は孤立電子対か結合の中点、終点は原子か結合の中点（新しい結合なら2原子の間）。矢じりが終点を指し、文字や他の矢印と重ならないこと。
- 図は左から右に読めるように並べ、幅が広すぎるときは2段に折り返す。

例（オキセタン + ブタナールと巻矢印1本）:
```svg
<svg xmlns="http://www.w3.org/2000/svg" width="220pt" height="80pt" viewBox="0 0 220 80">
  <rect width="220" height="80" fill="white"/>
  <g stroke="black" stroke-width="1" fill="none">
    <line x1="20" y1="30" x2="40" y2="30"/><line x1="20" y1="30" x2="20" y2="50"/><line x1="20" y1="50" x2="35" y2="50"/><line x1="40" y1="30" x2="40" y2="44"/>
    <line x1="80" y1="50" x2="97" y2="40"/><line x1="97" y1="40" x2="114" y2="50"/><line x1="114" y1="50" x2="131" y2="40"/>
    <line x1="131" y1="40" x2="131" y2="25"/><line x1="134" y1="40" x2="134" y2="25"/>
  </g>
  <text x="41" y="54" font-family="sans-serif" font-size="10" text-anchor="middle">O</text>
  <text x="60" y="44" font-family="sans-serif" font-size="12" text-anchor="middle">+</text>
  <text x="132" y="21" font-family="sans-serif" font-size="10" text-anchor="middle">O</text>
  <path d="M 128 34 C 115 20, 115 10, 126 12" stroke="black" stroke-width="1" fill="none"/>
  <polygon points="128,13 122,10 122,15" fill="black"/>
</svg>
```
