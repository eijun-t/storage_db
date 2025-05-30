# トランクルーム・データ

トランクルーム事業者のためのマーケット調査データ分析アプリ

## 📋 概要

このアプリケーションは、トランクルーム事業者向けに、物件開発やエリア選定の意思決定をサポートするためのデータ分析ツールです。トランクルーム市場は住宅やオフィスと比較して体系的なマーケット情報が少ないという課題を解決します。

## 🎯 主な機能

- **位置ベース検索**: 特定の住所を中心に半径指定で物件検索
- **物件データ可視化**: 近隣トランクルーム物件の詳細情報と履歴データ
- **エリア分析**: 面積帯、賃料単価、空室率の統計と推移
- **需給バランス分析**: 世帯数と物件数の比較によるヒートマップ表示

## 💡 ユースケース

トランクルーム事業者が以下のような場面で活用できます：
- 新規物件開発のエリア選定
- 競合分析と市場動向調査
- 料金設定の市場適正検証
- 需要予測と投資判断材料の収集

## 🔍 データソース

- [Japan Trunk Room](https://www.japantrunkroom.com/)からの物件情報（日次スクレイピング）
- 公的統計情報（町丁目単位の世帯数データ）
- 地理空間情報API

## 🛠️ 技術構成

- **フロントエンド**: Streamlit
- **バックエンド**: Python
- **データベース**: Supabase
- **認証**: Supabase Auth
- **地図表示**: Mapbox/Google Maps API
- **データ収集**: 自動スクレイピングバッチ処理

## 🚀 使い方

1. アカウント登録/ログイン
2. 調査したい住所を入力
3. 検索範囲（半径km）を指定
4. 物件リストや地図から詳細情報を確認
5. エリア全体のデータレポートを分析
6. 需給バランスヒートマップで開発ポテンシャルを評価

## 🔒 データモデル

```json
物件: {
  id: string,
  status: "空室" | "満室",
  size: number,  // 広さ(㎡)
  price: number, // 料金(円/月)
  address: string,
  latitude: number,
  longitude: number,
  history: [
    { date: string, status: string, price: number }
  ]
}
```

## 📊 分析指標

- エリア内物件数
- 平均/中央値賃料（総額・単価）
- 空室率と推移
- 面積帯別分布
- 世帯数あたり物件数（需給バランス）

## 🔜 開発予定機能

- PDF形式でのレポート出力
- 複数エリア比較分析
- 需要予測モデル
- モバイルアプリ対応
