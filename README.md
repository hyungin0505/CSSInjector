# CSSInjector

**Tool for CSS Injection**

CSS Injection으로 발생하는 외부 요청을 로컬 Flask 서버에서 실시간으로 수집하고,
수집된 요청 결과를 기반으로 다음 단계 CSS Injection 페이로드 생성을 돕는 도구입니다.  
<br>

> 본 도구는 CSS Attribute Selector(^=) 기반으로 페이로드를 생성하는데 최적화 기법과 같은 방법론들은 추후에 확장적으로 적용할 계획입니다.  

<br>

## Features

- CSS url() 요청을 이용한 외부 요청(콜백) 수집
- 실시간 요청 로그 수집
- 페이로드 자동 생성
- Flask 기반 로컬 서버
<br>

## Basic Concept

- CSS Attribute Selector (^=)를 사용해 값의 접두사를 검사
- 참일 경우 background-image: url(...)을 통해 외부 요청
- 요청 결과를 Flask 서버에서 수집
- 수집된 결과를 바탕으로 다음 단계 페이로드 확정
- 다음 단계 페이로드를 자동 생성하여 반복 수행
<br>

## Goals

- 일단 지금은 가장 단순한 prefix 기반 방식만 구현
- 이분 탐색, one-shot 기법 등은 좀 더 공부하고 기능 추가할 예정
- 아마 워게임이나 CTF 풀면서 새로운 방법론 익히며 추가하지 않을까..  

<!-- Injection Vector
- 현재: URL 파라미터 (?color=)
- HTML attribute
- <style> 태그 내부
- Template 변수 등

Character Set
- 현재: 알파벳 소문자 (a-z)
- 대문자
- 숫자
- 특수 문자 (_{}-@: 등)

Target Length
- 현재: 고정 길이 (예: 8자)
- 사용자 입력 기반 길이 설정
- 종료 조건 자동 판별

Callback Parameters
- 현재: 단일 핵심 파라미터
- 단계 정보
- 위치 인덱스
- 전략 식별자 등 복수 파라미터 처리 -->