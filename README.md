# 図美楽（ずみらく / zumiraku）

**システムとアプリを、AIまで含めて設計から運用まで引き受けるエンジニアです。実務12年。**

媒体によって 図美楽・ずみらく・ズミラク・図ミラク と表記が揺れていますが、どれも同じ人間です。英字は zumiraku で統一しています。

受託開発の会社でWebとシステムを、事業会社でインフラとセキュリティを担当したあと独立しました。決済連携API、予約管理システム、SaaS型の業務管理システム、月間1,200万PVのサイト運用、同時接続3,000人のリアルタイム基盤などを手がけています。ここ数年はRAGとLLMを業務に組み込む仕事も増えました。

## 守備範囲

### Service.01　Web・アプリ開発

React・Next.js・TypeScript、案件によっては WordPress・Shopify で。スマホアプリは React Native と Flutter を中心に、必要なら Swift・Kotlin でネイティブも書きます。

画面を作って終わりではありません。プッシュ通知、オフライン対応、App Store と Google Play の審査提出、公開後のアップデートまで通してやります。表示速度と検索での拾われ方も、同じように詰めます。

### Service.02　システム開発・インフラ

業務システムの新規開発から、動かなくなったものの改修、それを載せるサーバーまで。Python・Node.js・PHP でAPIを書き、PostgreSQL と MySQL を扱います。「前に作ってもらったけど、作った人と連絡がつかない」という状態からでも引き継ぎます。

AWSへの移行はダウンタイムをほぼ出しません。Docker と Terraform で環境を揃え、監視とバックアップ、自動デプロイまで含めて整えます。

### Service.03　AI活用・セキュリティ

社内の資料をAIに読ませて答えさせるRAG、問い合わせ対応の自動化、データ収集の自動化。OpenAI と Claude のAPI、LangChain、ベクトル検索を使い分けます。やらなくていい作業から順に外していきます。

あわせて脆弱性診断とその改修、WAFの導入、ログの監視まで。社内のデータをAIに渡す以上、ここは同時に進めるべきところです。

## これまで

| | |
|---|---|
| Webサイト・アプリ | 200件以上 |
| 業務システム | 90件以上 |
| クラウドの構築と移行 | 60件以上 |
| 脆弱性診断とその改修 | 40件以上 |

## 公開しているもの

受託案件が中心なので、守秘義務の範囲で公開できるものを置いています。

### システム開発・インフラ

#### [sktes-global-auction](https://github.com/zumiraku/sktes-global-auction)

中古IT機器の国際競売プラットフォーム。封印入札を実装しています。

入札額はロットごとの鍵で暗号化し、締切まで出品者にも管理者にも見えません。鍵は締切時刻を認証データに含めて封じているので、あとから締切を動かすと復号できなくなります。入札時に渡すハッシュで、開封後の金額が改変されていないことを応札者自身が検証できます。

Excel明細の取り込み、多要素認証、7年保存の監査ログ、日英中の3言語対応。Next.js 15 / Prisma / TypeScript。

#### [hitotsu](https://github.com/zumiraku/hitotsu)

業務管理システム。顧客・案件・タスク・対応履歴・ファイル・社内メモを1か所に集約します。

Excel やスプレッドシートに散らばった情報をまとめ、担当者が変わっても引き継ぎで困らない状態をつくることが目的です。Next.js 16 / Prisma 7 / PostgreSQL 17。

#### [work-report-system](https://github.com/zumiraku/work-report-system)

病院設備の保守点検報告書システム。現場のタブレットから入力してPDFまで出します。

本番がさくらのレンタルサーバという制約だったため、Composer も Node も使わず素のPHPで組んでいます。FTPで上げれば動く状態を維持するためです。PDFは TCPDF を同梱、Excel の読み書きは zip 拡張のみで実装しました。

### AI活用・セキュリティ

#### [faq-ai](https://github.com/zumiraku/faq-ai)

AI採用システム。会社説明会チャットとAI面接官です。

デモ版と本番版を別に作ると片方だけ直して食い違うので、同じコードで動かしています。切り替えの分岐は起動時の1回だけです。AI面接官はスコアを出しますが、合否は人が押します。スコアが低くても回答を読めば拾える候補者がいるためです。

### Web・アプリ開発

#### [takamatsu-law](https://github.com/zumiraku/takamatsu-law)

法律事務所サイトのリニューアル案。コラムを軸にした情報発信とブランディングを目的に構成しています。

コラムを独立した投稿タイプにして、分野ごとのアーカイブを持たせました。記事が増えても管理画面が散らかりません。各記事に絶対URLの canonical を出力しているので、将来 note に要約を載せても検索評価は本体サイトに集約されます。試作は TanStack Start、納品は WordPress。

#### [teachingbeauty-migration-to-wp](https://github.com/zumiraku/teachingbeauty-migration-to-wp)

鍼灸整骨院サイトの WordPress 移行。既存の予約導線を落とさないことが最優先の案件でした。

デザインもURLも変えず、全39ページを1対1で移しています。既存の `.html` URL を維持したので、検索評価も被リンクもブックマークもそのまま残りました。

#### [isplanning-migration](https://github.com/zumiraku/isplanning-migration)

ECサイトの MakeShop ベーシックモードからクリエイターモードへの移行。商品ページ9,514点を含む10,306URLが対象です。

MakeShop の管理画面には変更履歴がなく、テンプレートの貼り間違いはプラットフォーム側から復元できません。そのため全テンプレート・スタイル・スクリプトを git で管理し、いつでも戻せる状態にしています。

#### [hp-renewal-5607506](https://github.com/zumiraku/hp-renewal-5607506)

終活サービスのトップページをレスポンシブに改修。

`width=1480` 固定のビューポートをやめ、端末ごとにレイアウトを組み替えました。画像に焼き込まれていた文字（料金・電話番号など）はすべてテキスト化。本文は17〜18px、行間をゆったりめにしています。50〜70代の方がスマホで読むことを前提にしたためです。

#### [marsiees-bilingual](https://github.com/zumiraku/marsiees-bilingual) / [marsiees-en-lp](https://github.com/zumiraku/marsiees-en-lp)

既存サイトへの英語ページ追加と、海外企業向けの英語ランディングページ。

既存デザインをそのまま保ったまま、ヘッダーの JP / EN で切り替える構成にしています。

#### [zumiraku.github.io](https://github.com/zumiraku/zumiraku.github.io)

プロフィールページ。HTMLとCSSだけの1枚もの。

## 技術

**AI / LLM** ChatGPT / Claude / RAG / LangChain / ベクトル検索 / Python / FastAPI
**フロント** TypeScript / React / Next.js / React Native / Flutter / Vue.js / Tailwind CSS
**サーバー** Node.js / PHP / Laravel / Django / NestJS
**データベース** PostgreSQL / MySQL / Prisma / Supabase / Redis
**インフラ** AWS / Azure / Docker / Kubernetes / Terraform / Nginx
**セキュリティ** 脆弱性診断 / WAF / ログ監視

新しいものに飛びつくより、枯れたものを正しく使うほうが好きです。さくらのレンタルサーバのように制約の多い環境も慣れています。

## 資格

AWS Certified Solutions Architect – Professional / AWS Certified Security – Specialty / 情報処理安全確保支援士 / 応用情報技術者 ほか

ただ、一番の武器は資格ではなく、現場で書いてきたコードの量だと思っています。

## 仕事の進め方

**できないことは、先に「できません」と言います。** 安く受けて途中で止まるのが、いちばん迷惑をかけるので。

**着手する前に、何ができて何ができないかをすべて出しきります。** ここを飛ばすと作り直しになります。これまで受けた仕事を、途中で投げ出したことは一度もありません。

**セキュリティは、あとから足すものではありません。** 設計のいちばん最初に入れます。

**途中経過はスクショや短い動画で共有します。** 「聞いてない」をゼロにしたいので。

**バグは症状ではなく、原因から直します。** 同じところで二度止まらないように。

**納品して終わり、にはしません。** 動き続けて、はじめて役に立つものなので。

## 対応エリアと時間

オンラインで全国どこでも対応します。打ち合わせはビデオ通話、やりとりはチャットで完結。

返信は平日なら4時間以内、土日祝でも12時間以内に。

週1〜3日の業務委託や技術顧問のご相談も受けています。

## 発信

学んだことは溜め込まずに書いて出しています。実務でハマったところと、その抜け方が中心です。

| 媒体 | リンク | 表示名 |
|---|---|---|
| note | [note.com/zumiraku](https://note.com/zumiraku) | 図美楽 |
| Qiita | [qiita.com/zumiraku](https://qiita.com/zumiraku) | ずみらく |
| Zenn | [zenn.dev/zumiraku](https://zenn.dev/zumiraku) | ズミラク |
| YOUTRUST | [youtrust.jp/users/zumiraku](https://youtrust.jp/users/zumiraku) | 図ミラク |

お仕事のご相談は、要件が固まっていない段階からでも構いません。NDAも対応します。

---

## English

**Zumiraku (図美楽)** — a freelance engineer in Japan who builds systems and apps, AI included, from design through to operation. Twelve years in the field.

I started in contract development, building web products and business systems, then moved to an operating company to handle infrastructure and security before going independent. Past work includes payment-gateway integrations, reservation management, a SaaS operations platform, running a site at 12 million monthly page views, and a realtime backend holding 3,000 concurrent users. In recent years a growing share of the work has been putting RAG and LLMs into everyday business processes.

**What I do**

- **Web and app development** — React, Next.js and TypeScript, with WordPress or Shopify where the project calls for it; React Native and Flutter for mobile, dropping to Swift or Kotlin when native is required. Push notifications, offline behaviour, App Store and Google Play submission, and post-launch updates are part of the job, as are page speed and search visibility.
- **Systems and infrastructure** — new business systems, rescue work on ones that stopped running, and the servers underneath. APIs in Python, Node.js and PHP against PostgreSQL and MySQL. I take over projects whose original author is no longer reachable. AWS migrations run with next to no downtime, with Docker and Terraform for parity, plus monitoring, backups and automated deploys.
- **AI and security** — RAG over internal documents, automated enquiry handling and data collection, using the OpenAI and Claude APIs, LangChain and vector search. Alongside that: vulnerability assessment and remediation, WAF rollout and log monitoring. If company data is going to an AI, that part cannot be deferred.

**Track record** — 200+ websites and apps, 90+ business systems, 60+ cloud builds and migrations, 40+ vulnerability assessments and the fixes that followed.

**Public repositories** span all three areas: a sealed-bid auction platform for international IT asset trading (per-lot RSA encryption of bid amounts with the deadline bound into the key as authenticated data, Excel manifest import, TOTP multi-factor auth, a seven-year audit log, trilingual UI), a CRM-style operations system consolidating clients, projects, tasks and correspondence, a maintenance reporting system for hospital facilities written in dependency-free PHP to fit a constrained shared host, an AI recruiting system where the model scores candidates but a human makes every decision, and several site migrations — including an e-commerce move where the vendor console keeps no version history, so every template is tracked in git to stay recoverable.

**Certifications** — AWS Certified Solutions Architect – Professional, AWS Certified Security – Specialty, Registered Information Security Specialist (Japan), Applied Information Technology Engineer.

**How I work** — I say no before starting rather than stalling halfway. Everything that is and is not possible gets written down before any code is written. Security goes in at the start of the design, not on top of it afterwards. Progress is shared as screenshots and short clips. Bugs get fixed at the cause, not the symptom. Delivery is not the end; something only earns its keep by continuing to run.

Remote across Japan. Replies within 4 hours on weekdays, within 12 hours at weekends and on holidays. Open to contract work, including projects where the requirements are still taking shape, and to one-to-three-days-a-week engagements or advisory roles. NDAs are fine.
