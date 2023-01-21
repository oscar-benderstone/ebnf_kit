# ebnf_kit

> A successor to the [ebnf](https://github.com/ChAosUnIty/ebnf) parsing library. This crate aims to enhance ebnf parsing for sentences, add unicode support, and more.

I am making this for Welkin, a new language to meant for taking notes, storing mathematical strucutres, and more. More details to be posted.

## Warning: 
This tool is early development and will be available for sometime. Updates to be posted. For development logs, please see my blog [Logs of Humanistic Logic] (https://logsofhumanisticlogic.wordpress.com/). 

## Disclaimer:
There are various variants of EBNF, which uses somewhat different syntactic conventions. This library 
takes [EBNF Evaluator](https://mdkrajnak.github.io/ebnftest/)'s example code as standard, which has 
almost most syntactic conventions on Wikipedia's page.

## What does a valid EBNF grammar looks like?

The following example is taken from EBNF Evaluator:

```ebnf
filter ::= ( first ' ' )? ( number '~ ' )? ( number '-' number ) ( ' ' number '~' )? ( ' hz' )? ( ' b' )? ( ' i' )? ( ' a' )?
first  ::= #'[a-za-z][a-za-z0-9_+]*'
number ::= digits ( ( '.' | ',' ) digits? )?
digits ::= #'[0-9]+'
```

## How to use this library?

```rust
extern crate ebnf;

fn main() {
    let source = r"
        filter ::= ( first ' ' )? ( number '~ ' )? ( number '-' number ) ( ' ' number '~' )? ( ' hz' )? ( ' b' )? ( ' i' )? ( ' a' )?
        first  ::= #'[a-za-z][a-za-z0-9_+]*'
        number ::= digits ( ( '.' | ',' ) digits? )?
        digits ::= #'[0-9]+'
    ";

    let result = ebnf::get_grammar(source);
}
```
