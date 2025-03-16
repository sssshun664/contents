---
theme: seriph
background: /images/pancake.png
class: text-left
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
transition: slide-left
title: 冷凍パンケーキ通販における送料設定戦略
fonts:
  # 標準テキスト用
  sans: 'Noto Sans JP'
  # 見出し用
  serif: 'Noto Serif JP'
  # コードブロック用
  mono: 'Fira Code'
---

<style>
h1, h2, h3, p, ul, ol, div {
  text-align: left !important;
}

h2 {
  font-size: rem !important;
  margin-top: 0.5rem !important;
}

.fact-value {
  font-size: 1.8rem;
  font-weight: bold;
  color: #4169E1;
}

.highlight-box {
  background-color: rgba(100, 149, 237, 0.15);
  border-radius: 8px;
  padding: 12px;
  margin-top: 16px;
}

.text-center-important {
  text-align: center !important;
}
</style>

# 冷凍パンケーキ通販における<br>送料設定戦略

## カゴ落ち率改善に向けた最適送料分析

<div class="pt-12 pl-2">
  <span class="px-2 py-1 rounded cursor-default bg-blue-500 bg-opacity-10">
    🚚 送料適正化プロジェクト 2025.3
  </span>
</div>

<!--
このスライドは冷凍パンケーキ通販における送料設定の最適化について分析し、カゴ落ち率改善に向けた具体的な提案をまとめたものです。
-->

---
layout: fact
---

# 現状の送料

<div class="mt-6 text-center-important">
  <div class="fact-value">当社: 1,180円〜</div>
  <div class="text-xl mt-2">vs</div>
  <div class="fact-value mt-2">市場平均: 600〜1,000円</div>
</div>

---
layout: two-cols
---

# 現状分析

市場平均と比較して高めの送料設定がカゴ落ち率に影響している可能性が高い

<div class="mt-2">

### 当社の現行送料設定
- **基本送料:** 1,180円～
- **送料無料条件:** なし
- **特徴:** 市場平均と比較して**やや高め**

</div>

<div class="mt-4">

### 送料と商品価格の関係
- 業界標準: 商品価格の<b>20～50%</b>
- 高い送料は<Transform :scale="1.1">カゴ落ち率の主要因</Transform>
- 送料が明示されていないと不安感を誘発

</div>

::right::

<div class="pl-4">

# 市場の送料相場

<div class="mt-2">

### 大都市圏
<div class="text-xl font-bold text-blue-600">600〜1,000円</div>

### 遠隔地向け（北海道・沖縄・離島）
<div class="text-xl font-bold text-blue-600">1,500〜2,500円</div>

<div class="text-sm mt-4">参考: パンケーキカフェcafeblow, R.Lワッフル</div>

</div>

<div class="highlight-box mt-8">
  <div class="flex items-center">
    <div class="text-2xl text-red-500 mr-2">💡</div>
    <div>送料が商品価格を上回ると<br><b>購入意欲が大幅に低下</b>する</div>
  </div>
</div>

</div>

<!--
当社の送料設定と市場相場を比較し、現在の送料設定が業界平均より高い傾向にあることを示しています。これがカゴ落ち率に影響している可能性があります。
-->

---
layout: default
---

# 競合分析：多様な送料戦略

競合各社は様々な送料戦略でカゴ落ち防止と顧客獲得を実現している

<div class="overflow-x-auto">
  <table class="w-full">
    <thead>
      <tr>
        <th class="text-left pr-2">戦略タイプ</th>
        <th class="text-left px-2">代表企業</th>
        <th class="text-left px-2">送料設定</th>
        <th class="text-left pl-2">特徴・メリット</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="pr-2 py-2">全国一律型</td>
        <td class="px-2 py-2">ワッフル・ケーキの店R.L</td>
        <td class="px-2 py-2">全国一律980円</td>
        <td class="pl-2 py-2">シンプルで顧客にわかりやすい</td>
      </tr>
      <tr>
        <td class="pr-2 py-2">地域別変動型</td>
        <td class="px-2 py-2">霧や櫻や</td>
        <td class="px-2 py-2">関東1,960円<br>北海道2,560円</td>
        <td class="pl-2 py-2">配送コストに忠実だが複雑</td>
      </tr>
      <tr>
        <td class="pr-2 py-2">送料無料閾値型</td>
        <td class="px-2 py-2">パンケーキカフェcafeblow<br>花畑牧場</td>
        <td class="px-2 py-2"><b>5,000円以上</b><br>10,000円以上</td>
        <td class="pl-2 py-2">購入単価向上・まとめ買い促進</td>
      </tr>
    </tbody>
  </table>
</div>

<div class="mt-8 highlight-box flex items-center">
  <span class="text-xl mr-2">🔍</span>
  <div>
    <div class="font-bold">送料無料閾値型の有効性</div>
    <div class="mt-1">適切な閾値設定（5,000〜6,000円）で顧客のまとめ買いを促進し、<br>1回あたりの購入単価を向上させることが可能</div>
  </div>
</div>

<!--
競合他社の送料戦略を3つのパターンに分類し、それぞれの特徴とメリットを分析しています。特に送料無料閾値型は購入単価向上に効果的です。
-->

---
layout: statement
---

## 改善提案：送料引下げとキャンペーン戦略で<br>カゴ落ち率30%削減を目指す

適切な送料設定と戦略的なキャンペーンで、購入障壁を低減し売上増加を実現

<div class="grid grid-cols-2 gap-10 pt-6">
<div>

### 📦 基本送料改善案
- **基本送料:** 全国一律800円
  <small>(北海道・沖縄 +500円)</small>
- **送料無料条件:** 6,000円以上の購入

</div>
<div>

### 🚀 追加戦略オプション
- **期間限定キャンペーン**<br>
  季節イベント時の送料無料企画
- **送料込みセット商品**<br>
  贈答用などで送料込み価格を設定
- **初回限定優遇**<br>
  新規顧客向け送料無料クーポン

</div>
</div>


<!--
具体的な改善提案として、全国一律800円の基本送料と6,000円以上で送料無料という条件を提案しています。また、追加戦略として季節キャンペーンや送料込みセットなどの施策も推奨しています。これらにより、カゴ落ち率30%削減を目指します。
-->

---
layout: fact
---

# Thank you🎉

---