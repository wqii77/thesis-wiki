---
title: "共變數分析（Analysis of Covariance）"
type: method
aliases: ["Analysis of Covariance", "ANCOVA", "單因子共變數分析"]
tags: [method]
updated: 2026-11-09
---

## 這個方法在做什麼

共變數分析（Analysis of Covariance, ANCOVA）比較不同組別的結果時，會先扣掉另一個變項（共變數）帶來的差異。就像比較兩班的期末成績時，先考慮兩班原本的起點，再看誰進步得多。語言教學的介入研究常把前測當作共變數。（本段是通用統計說明，整理者補充。）

## 什麼時候適合用

- 有兩組以上、依變項是連續分數，而且有前測等可以控制的變項。
- 要確認共變數與依變項的關係在各組相近（迴歸斜率同質）。
- 沒有隨機分派時，統計控制不等於組別原本就相同。
- 同時檢定多個依變項時，要考慮多重檢定的校正。

（以上是通用統計說明，整理者補充。）

## 使用此方法的文獻

| 文獻 | 用來回答什麼問題 | 備註 |
|---|---|---|
| [[fathi2024improving\|Fathi et al. (2024)]] | 控制前測後，AI 組與面對面組的口說與溝通意願（Willingness to Communicate, WTC）是否不同（PDF p. 8, 10–11） | N = 65（PDF p. 5）；有多處 ηp² 與 F 值對不上（整理者計算）；文中未報告迴歸斜率同質性檢定 |
| [[zhang2024artificial\|Zhang et al. (2024)]] | 控制前測後，實驗組與對照組的外語愉悅（Foreign Language Enjoyment, FLE）、外語焦慮（Foreign Language Anxiety, FLA）與溝通意願是否不同（PDF p. 6, 8） | N = 131（PDF p. 4）；SPSS 27.0（PDF p. 6）；文中未報告迴歸斜率同質性檢定，也沒有校正多重檢定 |

> [!idea] 我的想法
> （待使用者補寫）
