# chem-figure-svg

化学の構造式・反応機構の図を、説明書（BRIEF.md）にそって SVG で直接描き、PNG にして見て直す skill。

## 中身
- `SKILL.md`: 作業の手順
- `BRIEF.md`: SVG の書き方の説明書
- `scripts/svg2png`: SVG を PNG にする変換（resvg。書体は Noto Sans CJK JP を指定）

## 入れ方
このリポジトリを `~/.claude/skills/chem-figure-svg`（かプロジェクトの `.claude/skills/chem-figure-svg`）に clone する。例: `git clone <このリポジトリの URL> ~/.claude/skills/chem-figure-svg`

## 依存
- Node.js
- npm パッケージ `@resvg/resvg-js`（動作を確かめたのは 2.6.2）。clone したディレクトリ（リポジトリの直下）で `npm install --prefix . --no-save @resvg/resvg-js@2.6.2` を実行する（`node_modules/` ができる）。
- フォント Noto Sans CJK JP（Debian・Ubuntu なら `fonts-noto-cjk`）。無いと日本語の文字が出ない。

## 使い方
`scripts/svg2png IN.svg OUT.png`。出力の `ok ...` なら PNG ができている。`error:` は SVG の構文の誤り。
