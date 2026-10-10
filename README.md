# 図美楽（ずみらく / zumiraku）

大阪のフリーランスAIエンジニアです。生成AIを使った業務自動化と、Webシステムの受託開発をしています。

媒体によって 図美楽・ずみらく・ズミラク・図ミラク と表記が揺れていますが、どれも同じ人間です。英字は zumiraku で統一しています。

実務8年。PHP・Python・WordPress は学生時代から10年以上、AI開発は6年目です。

## やっていること

RAG による社内文書検索、LLM を使った業務自動化、エージェントの開発が中心です。あわせて React/Next.js・Shopify・WordPress でのサイト構築、AWS へのサーバー移行まで、設計から運用までひとりで担当します。

精度や速度を出すところまでが仕事だと考えています。動くものを作るだけなら誰でもできるようになったので、そこから先で差が出ます。

## 実績

| | |
|---|---|
| RAGチャットボット | 回答精度 98% |
| AIマッチングシステム | 成約率 42% 向上 |
| Slack / LINE ボット | 1日 2,000件以上のメッセージを自動処理 |
| WordPress制作 | 不動産・医療・サロン系で 30サイト以上 |
| サーバー移行 | ダウンタイムほぼゼロ |
| Web・アプリ制作 | 170件以上 |
| システム・ツール開発 | 80件以上 |

## 公開しているもの

### [sktes-global-auction](https://github.com/zumiraku/sktes-global-auction)

中古IT機器の国際競売プラットフォーム。封印入札を実装しています。

入札額はロットごとの鍵で暗号化し、締切まで出品者にも管理者にも見えません。鍵は締切時刻を認証データに含めて封じているので、あとから締切を動かすと復号できなくなります。入札時に渡すハッシュで、開封後の金額が改変されていないことを応札者自身が検証できます。

Excel明細の取り込み、多要素認証、7年保存の監査ログ、日英中の3言語対応。Next.js 15 / Prisma / TypeScript。

### [work-report-system](https://github.com/zumiraku/work-report-system)

病院設備の保守点検報告書システム。現場のタブレットから入力してPDFまで出します。

本番がさくらのレンタルサーバという制約だったため、Composer も Node も使わず素のPHPで組んでいます。FTPで上げれば動く状態を維持するためです。PDFは TCPDF を同梱、Excel の読み書きは zip 拡張のみで実装しました。

### [faq-ai](https://github.com/zumiraku/faq-ai)

AI採用システム。会社説明会チャットとAI面接官です。

デモ版と本番版を別に作ると片方だけ直して食い違うので、同じコードで動かしています。切り替えの分岐は起動時の1回だけです。AI面接官はスコアを出しますが、合否は人が押します。スコアが低くても回答を読めば拾える候補者がいるためです。

### [teachingbeauty-migration-to-wp](https://github.com/zumiraku/teachingbeauty-migration-to-wp)

鍼灸整骨院サイトの WordPress 移行。既存の予約導線を落とさないことが最優先の案件でした。

### [macOS-OpenAI-Text-to-Speech-](https://github.com/zumiraku/macOS-OpenAI-Text-to-Speech-)

Mac で選択したテキストをショートカット一発で読み上げるツール。

## 技術

**AI / LLM** ChatGPT / Claude / RAG / Python / FastAPI / MLOps
**フロント** TypeScript / React / Next.js / Vue.js / Tailwind CSS
**サーバー** Node.js / PHP / Laravel / Django / NestJS
**データベース** PostgreSQL / MySQL / Prisma / Supabase / Redis
**インフラ** AWS / Azure / Docker / Kubernetes / Nginx / Terraform

新しいものに飛びつくより、枯れたものを正しく使うほうが好きです。さくらのレンタルサーバのように制約の多い環境も慣れています。

## 資格

AWS Certified Solutions Architect – Professional / AWS Machine Learning Engineer / AWS Developer / Microsoft Azure / 応用情報技術者 / 基本情報技術者 / Python 3 エンジニア認定基礎試験 / CIW JavaScript Specialist / Adobe Certified Professional / TOEIC 830

一番の武器は資格ではなく、10年以上コードを書き続けた経験値のほうだと思っています。

## 仕事の進め方

着手前に要件を言語化して、認識を合わせてから書き始めます。途中経過はスクリーンショットや動画で共有します。

バグは症状ではなく原因から直します。同じところを再発させないためです。

返信は平日なら30分〜4時間。土日祝も夜は動いています。

## リンク

| 媒体 | リンク | 表示名 |
|---|---|---|
| note | [note.com/zumiraku](https://note.com/zumiraku) | 図美楽 |
| Qiita | [qiita.com/zumiraku](https://qiita.com/zumiraku) | ずみらく |
| Zenn | [zenn.dev/zumiraku](https://zenn.dev/zumiraku) | ズミラク |
| YOUTRUST | [youtrust.jp/users/zumiraku](https://youtrust.jp/users/zumiraku) | 図ミラク |

お仕事のご相談は直接お寄せください。要件が固まっていない段階からでも構いません。NDAも対応します。

---

## English

Zumiraku (図美楽) — freelance AI engineer based in Osaka, Japan.

Eight years of professional work, with ten-plus years in PHP, Python and WordPress, and six years in AI development. I build LLM applications and workflow automation with ChatGPT, Claude and RAG, alongside web work in React/Next.js, Shopify and WordPress, and AWS migrations — design through to operation, handled solo.

Across that time I have shipped 170+ web and app projects and 80+ systems and internal tools. Selected results: a RAG chatbot answering at 98% accuracy, an AI matching system that lifted conversion by 42%, Slack and LINE bots processing over 2,000 messages a day, and 30+ WordPress sites across real estate, healthcare and salon businesses.

Public repositories include a sealed-bid auction platform for international IT asset trading (per-lot RSA encryption of bid amounts with the deadline bound into the key as authenticated data, Excel manifest import, TOTP multi-factor auth, seven-year audit log, trilingual UI), a maintenance reporting system for hospital facilities written in dependency-free PHP to fit a constrained shared host, and an AI recruiting system where the model scores candidates but a human makes every decision.

Certifications: AWS Solutions Architect – Professional, AWS Machine Learning Engineer, AWS Developer, Microsoft Azure, and the Applied Information Technology Engineer Examination.

I care more about whether something holds up in production than about which framework it uses. Open to contract work, including projects where the requirements are still taking shape. NDAs are fine.
