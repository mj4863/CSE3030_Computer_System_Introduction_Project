# CSE3030_Computer_System_Introduction_Project
2024-1 컴퓨터시스템개론

# Lab 1: Bit Lab

이 디렉토리에는 CSAPP 스타일의 Bit-Level Puzzles 세 가지 문제를 해결하기 위한 C 소스파일이 포함되어 있다. 각 문제는 주어진 제약조건 내에서 비트 연산만으로 구현해야 한다.

---

## 디렉토리 구조

```
Lab1/
├── 1-1_bitMask/
│   ├── bitMask.c       # bitMask 함수 구현 파일
│   ├── main.c          # 테스트 드라이버
│   ├── Makefile        # 빌드 스크립트
│   └── testcase/       # 제공된 테스트 케이스
│       ├── tc-*.txt
│       └── ans-*.txt
│
├── 1-2_absVal/
│   ├── absVal.c        # absVal 함수 구현 파일
│   ├── main.c
│   ├── Makefile
│   └── testcase/
│
├── 1-3_conditional/
│   ├── conditional.c   # conditional 함수 구현 파일
│   ├── main.c
│   ├── Makefile
│   └── testcase/
│
├── validate            # 제약조건 검사 스크립트
└── check.py            # 자가 채점 스크립트
```

---

## 문제별 구현 요약

### 1-1. bitMask

* **함수 시그니처**: `int bitMask(int x)`
* **목표**: 상위 32‑x 비트는 0, 하위 x 비트는 1인 마스크 생성
* **제약**: `! ~ & ^ | + << >>` 만 사용, if/loop/함수 호출 금지

### 1-2. absVal

* **함수 시그니처**: `int absVal(int x)`
* **목표**: x의 절댓값 반환 (2의 보수 표현 고려)
* **제약**: 부호 비트 추출 및 비트 연산만 사용

### 1-3. conditional

* **함수 시그니처**: `int conditional(int x, int y, int z)`
* **목표**: x가 0이면 z, 아니면 y 반환
* **제약**: 분기문/조건식 없이 구현

---

## 컴파일 및 실행

각 문제 디렉토리에서 다음 명령으로 빌드 및 테스트한다.

```bash
cd Lab1/1-1_bitMask
make

# 특정 테스트 케이스 실행
echo <input> | ./bitMask
# 또는 제공 테스트 파일 테스트
time ./main testcase/tc-1.txt > output.txt
diff output.txt testcase/ans-1.txt
```

---

## 제약조건 검사

* `./validate bitMask.c` 형태로 실행
* 제약 연산자 위반 시 오류 메시지 출력
* 출력 없으면 제약조건 통과

---

## 자가 채점

```bash
cd Lab1
python3 check.py
```

* 각 문제별 테스트 결과 문자를 확인

  * O: 정답, X: 오답, C: 컴파일 오류, T: 타임아웃, I: 제약조건 위반, E: 런타임 오류
* 모든 테스트에서 `O`가 나오도록 구현

---

**끝**
