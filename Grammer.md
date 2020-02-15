# Stack oriented

모든 표현식은 후위표현식입니다


# Keywords

- `선택`
- `그외`
- `종료`
- `반복`

# Comment

`; Comment`

# Operators

## Simple operator

### Add

`+`

### Sub

`-`

### Div

`/`

### Mul

`*`

### Rem

`%`

### And

`&`

### Xor

`^`

## Boolean op

### Not

`~`

### Equal

`==`

### Not Equal

`<>`

### Less

`<`

### Greater

`>`

### Less or Equal

`<=`

### Greater or Equal

`>=`

## Stack op

### \[?]

넣은 순서대로 A, B, C 3개를 꺼내서 A가 참일경우 B를 거짓일경우 C를 스택에 넣음

### \[-]

스택에서 1개를 꺼내서 버림 없을경우 무시됨

### \[+]

스택의 맨위에 있는 값을 복사해서 집어넣음

### \[\<variable>]

스택의 맨위에 있는 값을 \<variable>에 집어넣음


# Builtin value

identifier = \[a-zA-Zㄱ-ㅎㅏ-ㅣ가-힣_]\[0-9a-zA-Zㄱ-ㅎㅏ-ㅣ가-힣_\]*

# Variable

*항상* `$`가 앞에옴

identifier = \[0-9a-zA-Zㄱ-ㅎㅏ-ㅣ가-힣_\]+


# Types

- int
- str

조건연산자는 1과 0으로 변환됩니다

빈 문자열과 0은 거짓이고 나머지는 모두 참입니다

수의 범위는 0 ~ 4,294,967,295 (2^32 − 1) 까지입니다 음수는 없습니다


# Block

중괄호({ })로 둘러쌓인 코드입니다

끝날때 스택이 정리됩니다


# Statement

## Exit

스크립트를 종료합니다

`종료`

```
종료
; 여기부터는 출력안됨
1 2 + @
```

## Store Variable

스택에서 맨위의 값을 뽑아서 변수에 저장합니다

`<expr> -> <variable>`

```
1 2 + -> $0
; $0 = 3
```

## Branch

### IF

`<expr> <block>`

```
2 1 > {
  '2는 1보다 크다'
}
```

### ELSEIF

`그외 <expr> <block>`

```
3 -> $수

$수 2 % 0 == {
    '짝수입니다'
} 그외 $수 30 > {
    '홀수입니다'
}
```

### ELSE

`그외 <block>`

```
50 -> $점수

$점수 70 > {
    "A"
} 그외 $점수 50 > {
    "B"
} 그외 {
    "C"
}

-> $등급

'등급: ' $등급 ''

;출력: '등급: C'
```

### SELECTCASE

```
선택 <expr> {
    (
        (int|str) (| (int|str))* <block>
    )*
    (
        그외       <block>
    )?
}
```

예시
```kes
선택 5 {
    1 | 2 | 3 {
        4:
    }
    5 | 6 {
        7:
    }
    그외 {
        8:
    }
}

;출력 = 7
```

### WHILE

```
반복 <expr> <block>
```

<expr>이 참인 동안 <block>을 계속 실행합니다


## Print


### PRINT

스택에 있는 모든 값들을 넣은 순서대로 출력합니다

`:`

```
1 2 'ㄱㄴㄷ':

; 출력: 12ㄱㄴㄷ
```

### NEWLINE

스택에 있는 모든 값들을 넣은 순서대로 출력하고 개행합니다

`@`

### WAIT

스택에 있는 모든 값들을 넣은 순서대로 출력하고 입력을 기다립니다

`#`


# Expression

## Literal

### Int literal

`\d+`

### Str literal

`'[^']*'`

## Builtin function

`(<argument>)*<ident>`

## Variable expr

`<variable>`

## Operator

`(<operand>)+<op>`
