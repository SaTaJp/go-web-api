# Go-web-API

本プロジェクトは、4人チームで開発した英語スラング辞書APIです。

## Original Repository
本リポジトリはチーム開発プロジェクトのフォークです。
Original Repository:
https://github.com/recursion-gowebapi/go-web-api

### 開発期間
2026年5月16日 ～ 2026年5月30日

### 担当箇所

#### データ設計
* slangs.json のデータ構造設計
* スラング情報のカテゴリ分類設計
* meaning、scene、emotion_categories 等の属性定義
* APIで利用しやすいJSONスキーマ設計
* Go構造体との整合性を考慮したデータモデル設計

#### Search API
* `GET /api/slangs/search?keyword={word}` の実装
* キーワード検索機能の実装
* normalizeText関数を用いた検索処理の実装
* 大文字小文字および前後空白を考慮した検索機能の実装

#### Random Slang API
* `GET /api/slangs/random?count={number}` の実装
* countパラメータのバリデーション処理
* ランダムシャッフル機能の実装
* JSONレスポンス生成処理の実装

## Overview

Native Slang API は、日本人英語学習者向けの英語スラング辞書 API です。

スラングの意味・ニュアンス・使用場面・感情カテゴリ・例文などを取得できるほか、検索やフィルタリング、ランダム取得、新規追加などの機能を提供します。

## Demo / Screenshot
![](https://github.com/user-attachments/assets/dd07a678-dbac-4fe2-bc80-b72c8d05c9bf)

## Features

- スラング一覧取得
- スラング詳細取得
- キーワード検索
- 使用場面（scene）による検索
- 感情カテゴリ（emotion）による検索
- ランダムスラング取得
- 関連スラング取得
- カテゴリ一覧取得
- 新規スラング登録

## Tech Stack

![Go](https://img.shields.io/badge/Go-1.25-00ADD8?logo=go&logoColor=white)
![HTML](https://img.shields.io/badge/HTML-5-E34F26?logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES2023-F7DF1E?logo=javascript&logoColor=white)
  
## Setup

**必要環境**
- Go 1.25以上

**手順**
1. リポジトリをクローン
```
git clone https://github.com/recursion-gowebapi/go-web-api.git
cd go-web-api
```
2. サーバーを起動
```
go run .
```
3. ブラウザで開く <br/>
http://localhost:8080

## API Documentation

API 仕様は OpenAPI (Swagger) 形式で管理しています。

- GitHub Pages: https://recursion-gowebapi.github.io/go-web-api/
- OpenAPI file: `docs/swagger.yaml`

Swagger Editor に読み込むことで、エンドポイントやリクエスト・レスポンス仕様を確認できます。

## Design / Implementation Notes

- Go 標準ライブラリ（net/http）のみを利用して API を実装
- データストアとして JSON ファイルを採用
- 共通モデルを利用し、レスポンス構造を統一
- handler / model / store を分離し責務を明確化
- 使用場面や感情カテゴリを利用した関連スラング検索機能を実装
- API 動作確認用のシンプルな Web UI を実装
