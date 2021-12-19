# README

# アプリケーション名
# アプリケーションの概要
 ミスをフォーマットに沿って記録するアプリです。簡単なフォーマットでミスの属性を分析することができます。
# URL
# テスト用アカウント
# 利用方法
# 目指した課題解決
 解決を目指していた課題は「仕事のミスをなくす」ことです。そしてミスを次に生かす導線として「ミスの原因を考える手間を省く」フォーマットが必要だと考えました。まずはユーザーが「選択肢から選ぶ」という単純な作業をするだけでミスの原因を浮き彫りにできるようにしたいです。
 
# ミスの構成要素

# 洗い出した要件

| 機能 | 目的 | 詳細 | ユースケース |
| :---- | :---- | :----| :---- |
| ユーザー登録機能
| ミスの登録機能
| ミスの個別詳細表示機能
| ミスの集計結果表示機能
| 解決策登録機能
| コメント機能

# データベース設計

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| nickname | string | null: false |
| email    | string | null: false |
| password | string | null: false |

### Association

- has_one  :questions

## questions テーブル

| Column        | Type       | Options     |
| ------------- | ---------- | ----------- |
| philosophy_id | integer    | null: false |
| color_id      | integer    | null: false |
| my_type_id    | integer    | null: false |
| like_type_id  | integer    | null: false |
| prefecture_id | integer    | null: false |
| food_id       | integer    | null: false |
| hobby_id      | integer    | null: false |
| music_id      | integer    | null: false |
| angry_id      | integer    | null: false |
| improve_id    | integer    | null: false |
| text          | text       |             |
| user          | references |             |

## Association
- belongs_to :philosophy
- belongs_to :color
- belongs_to :my_type
- belongs_to :like_type
- belongs_to :prefecture
- belongs_to :food
- belongs_to :hobby
- belongs_to :music
- belongs_to :angry
- belongs_to :improve
- belongs_to :user, optional: true