# Stack oriented

모든 표현식은 후위표현식입니다


# Keywords

- `선택`
- `그외`

# Comment

`; Comment`

# Operators

## Simple operator

### Add

`+`

### Sub, Neg

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

## Conditional op

## Not

`!`

## Equal

`==`

## Not Equal

`!=`

## Less

`<`

## Greater

`>`

## Less or Equal

`<=`

## Greater of Equal

`>=`


## Assign op

### Simple assign

`=`

### Combined assign

`<simple operator>=`


```
$1 = 0

$1 += 3 // shortcut for $1 = $1 3 + if $1 not exists it will error
```

# Builtin value

identifier = \[ㄱ-ㅎㅏ-ㅣ가-힣_]\[0-9ㄱ-ㅎㅏ-ㅣ가-힣_\]*

# Variable

*always* have `$` prefix

identifier = \[0-9ㄱ-ㅎㅏ-ㅣ가-힣_\]+


# Types

- int
- str

조건연산자는 1과 0으로 변환됩니다

빈 문자열과 0은 거짓이고 나머지는 모두 참입니다


# Block

중괄호({ })로 둘러쌓인 표현식입니다

종료시 스택이 정리됩니다


# Statement

## Variable

### Assign, Create

```
<variable> = <expr>
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
$수 = 3

$수 2 % 0 == {
    '짝수입니다'
} 그외 $수 30 > {
    '홀수입니다'
}
```

### ELSE

`그외 <block>`

```
$점수 = 50

$점수 70 > {
    $등급 = "A"
} 그외 $점수 50 > {
    $등급 = "B"
} 그외 {
    $등급 = "C"
}

'등급: ' $등급 ''$
```

### SELECTCASE

```
선택 <expr> {
    (
        (int|str) <block>
    )*
    (
        그외       <block>
    )?
}
```

## Print

스택에 있는 모든 문자값을 뽑아내서 출력합니다


### PRINT

`@`

### PRINTL

`$`

### PRINTW

`#`


# Expression

## Literal

### Int literal

`\d+`

### Str literal

`'[^']*'`

## Builtin function

`(<expr>)*<ident>`

## Variable expr

`<variable>`

## Binart op expr

`<expr><expr><binary-op>`
