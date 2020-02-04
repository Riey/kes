# Keywords

- `선택`
- `그외`
- `true`
- `false`


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

### Not

`!`


## Assign

### Simple assign

`=`

### Combined assign

`<simple operator>=`


```
$1 = 0

$1 += 3 // shortcut for $1 = $1 + 3 if $1 not exists it will error
```

# Variable

*always* have `$` prefix

identifier = (_ + 0-9 + 한글)+

# Types

- int
- str


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

`<blockend_from_prev_branch> <expr> <block>`

```
수 = 3

수 % 2 == 0 {
    '짝수입니다'
} 수 > 30 {
    '홀수입니다'
}
```

### ELSE

`<blockend_from_prev_branch>  그외 <block>`

```
점수 = 50

점수 > 70 {
    등급 = "A"
} 점수 > 50 {
    등급 = "B"
} 그외 {
    등급 = "C"
}

'등급: {}', 등급
```

### SELECTCASE

```
선택(<expr>) {
    (
        (int|str) <block>
    )+
}
```

## Print

### PRINTFORM

```
`FORMED STRING`((, form arguments)+?)
```

### PRINTFORML

```
"FORMED STRING"((, form arguments)+?)
```

### PRINTFORMW

```
'FORMED STRING'((, form arguments)+?)
```


# Expression

## Literal

### Int literal

`(-)?\d+`

### Str literal

`"[^"]*"`

#### Escape

`\`

## Builtin function

`<ident>((arg,)*)`

## Builtin variable

`<ident>`

## Variable expr

`<variable>`

## Unary op expr

`<unary-op><expr>`

## Binart op expr

`<expr><binary-op><expr>`


### Conditional op expr

`<expr> ? <expr> # <expr>`
