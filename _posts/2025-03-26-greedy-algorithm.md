---
layout: post
title: "그리디 알고리즘 이해하기"
date: 2025-03-26
categories: algorithm greedy
tags: [algorithm, greedy]
---

# 그리디 알고리즘이란?

그리디 알고리즘(Greedy Algorithm)이란, 문제를 해결하는 각 단계에서 가장 최선의 선택을 하는 알고리즘입니다.

## 특징

- 탐욕적 선택(Greedy Choice)
- 최적 부분 구조(Optimal Substructure)

## 예시: 동전 거스름돈 문제

500원, 100원, 50원, 10원짜리 동전으로 최소 개수의 동전을 구하는 문제입니다.

```python
def coin_change(coins, amount):
    count = 0
    coins.sort(reverse=True)
    for coin in coins:
        count += amount // coin
        amount %= coin
    return count

print(coin_change([500, 100, 50, 10], 1260))  # 출력: 6
