# kabubunseki7 — 投資データ検証チャンネル 自動化パイプライン

海外の一次データ(米市場・SEC EDGAR・FRED・CFTC)を取得し、日本株への影響を「過去データの検証」で可視化する非属人YouTubeチャンネルの制作システム。**予想はしない。数字だけを見せる。**

## 構成

| パス | 内容 |
|---|---|
| [market-video/](market-video/) | パイプライン本体(データ取得→集計→台本→音声→Remotion動画→サムネ) |
| [market-video/SETUP.md](market-video/SETUP.md) | **ローカルセットアップ手順**(FRED APIキー取得・毎朝の自動起動登録) |
| [docs/channel-requirements.md](docs/channel-requirements.md) | チャンネル要件定義(コンセプト・投稿設計・信頼設計・規制・KPI) |
| [docs/pipeline-v1-design.md](docs/pipeline-v1-design.md) | パイプライン設計書(設計思想・データソース・レビュー反映・運用タイムライン) |
| [docs/video-automation-research.md](docs/video-automation-research.md) | 市場調査(収益実態・規制・技術・競合・ジャンル分析) |

## 毎朝の使い方

```bash
cd market-video
npm install        # 初回のみ
npm run morning    # 取得→集計→ナレーション→動画+サムネ生成
```

生成された `out/short-日付.mp4` をプレビューし、YouTube Studioからアップロード。詳細は SETUP.md。

## 現在地(V1完成)

- [x] 日次Shorts自動生成(5指標+米セクターTOP3+注目業種コメント+音声+免責)
- [ ] ElevenLabs声クローン接続(録音待ち)
- [ ] V1.5: 長尺「米CPIの翌日、日経平均は過去10回どう動いたか」
- [ ] チャンネル開設・YouTube API監査申請

## 設計原則

1. 人間は判断だけ(テーマ・台本検収・公開)、機械は作業だけ
2. 動画に出る数値は全て機械計算・出典付き(LLMに数字を書かせない)
3. 予想・売買推奨をしない(投資助言規制の遵守)
4. ローカル完結・月額コスト1,000円台
