# Keywords

- `선택`
- `그외`

# Comment

`// Comment`

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

$1 += 3 // shortcut for $1 = $1 + 3 if $1 not exists it will error
```

# Builtin value

identifier = \[ㄱ-ㅎㅏ-ㅣ가-힣_]\[0-9ㄱ-ㅎㅏ-ㅣ가-힣_\]*

# Variable

*always* have `$` prefix

identifier = \[0-9ㄱ-ㅎㅏ-ㅣ가-힣_\]+

# Types

- int
- str

boolean expression is converted 1 or 0

empty str is false other strs are true

0 int is false other ints are true


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
2 > 1 {
  '2는 1보다 크다'
}
```

### ELSEIF

`그외 <expr> <block>`

```
$수 = 3

$수 % 2 == 0 {
    '짝수입니다'
} 그외 $수 > 30 {
    '홀수입니다'
}
```

### ELSE

`그외 <block>`

```
$점수 = 50

$점수 > 70 {
    $등급 = "A"
} 혹은 $점수 > 50 {
    $등급 = "B"
} 그외 {
    $등급 = "C"
}

'등급: {}', $등급
```

### SELECTCASE

```
선택(<expr>) {
    (
        (int|str|그외) <block>
    )+
}
```

## Print

### PRINTFORM

```
'FORMED STRING'((, <expr>)+?)
```

### PRINTFORML

```
'FORMED STRING'$((, <expr>)+?)
```

### PRINTFORMW

```
'FORMED STRING'#((, <expr>)+?)
```


# Expression

## Literal

### Int literal

`\d+`

### Str literal

`'[^']*'`

## Builtin function

`<ident>((<expr>,)*)`

## Builtin variable

`<ident>`

## Variable expr

`<variable>`

## Binart op expr

`<expr><binary-op><expr>`


## Conditional op expr

`<expr> ? <expr> # <expr>`
