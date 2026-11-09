---
title: "成對樣本 t 檢定（Paired-Samples t-Test）"
type: method
aliases: ["Paired-Samples t-Test", "Paired Sample t-Test", "成對樣本 t 檢定"]
tags: [method]
updated: 2026-11-09
---

## 這個方法在做什麼

成對樣本 t 檢定（Paired-Samples t-Test）比較同一批人在兩個時間點或兩個條件下的平均差異。就像用同一批學生的期初與期末分數，看這段時間平均變了多少。（本段是通用統計說明，整理者補充。）

## 什麼時候適合用

- 同一批人測兩次，或資料能一對一配對，而且結果是連續分數。
- 它只能說明這批人有沒有改變，不能單獨說明改變來自介入。
- 不能因為一組顯著、另一組不顯著，就下結論說兩組不同；組間差異要直接檢定。
- 同時檢定多個結果時，要考慮多重檢定的校正。

（以上是通用統計說明，整理者補充。）

## 使用此方法的文獻

| 文獻 | 用來回答什麼問題 | 備註 |
|---|---|---|
| [[fathi2024improving\|Fathi et al. (2024)]] | AI 組與面對面組各自的口說與溝通意願（Willingness to Communicate, WTC）是否進步（PDF p. 8–10） | 另以[[ancova\|共變數分析（Analysis of Covariance, ANCOVA）]]比較組間差異（PDF p. 8） |
| [[zhang2024artificial\|Zhang et al. (2024)]] | 實驗組與對照組各自的外語愉悅（Foreign Language Enjoyment, FLE）、外語焦慮（Foreign Language Anxiety, FLA）與 WTC 是否改變（PDF p. 6, 9） | 實驗組 n = 65、對照組 n = 66（PDF p. 9）；另以[[ancova\|共變數分析]]比較組間差異（PDF p. 8） |

> [!idea] 我的想法
> （待使用者補寫）
