
# Go

based on the course from [Aprenda Go](https://www.youtube.com/c/AprendaGo) and  [Fiusky's Lab](https://www.youtube.com/c/AprendaGohttps://github.com/fiuskylab/)

---

# Cap. 2 – Variáveis, Valores & Tipos – 1. Go Playground

## Operador curto de declaração

    - := parece uma marmota (gopher).
    - Tipagem automática
    - Só pode repetir se houverem variáveis novas 
    - != do assignment operator (operador de atribuição)
    - Só funciona dentro de codeblocks

# Lição principal

- := utilizado pra criar novas variáveis, dentro de code blocks
= para atribuir valores a variáveis já existentes

---

# Cap. 2 – Variáveis, Valores & Tipos – 2. Hello world

## Explorando tipos

- Tipos em Go são estáticos.

- O tipo pode ser deduzido pelo compilador:
  - x := 10 -> Int
  - var y = "string"
- Ou pode ser declarado especificamente:
  - var w string = "isso é uma string"
  - var z int = 15
  - na declaração var z int com package scope, atribuição z = 15 no codeblock (somente)
- Tipos de dados primitivos: disponíveis na linguagem nativamente como blocos básicos de construção
  - int, string, bool
- Tipos de dados compostos: são tipos compostos de tipos primitivos, e criados pelo usuário
  - slice, array, struct, map
- O ato de definir, criar, estruturar tipos compostos chama-se composição.

---

# Cap. 2 – Variáveis, Valores & Tipos – 6. Valor zero

## Valor zero

- Declaração vs. inicialização vs. atribuição de valor. Variáveis: caixas postais.
- O que é valor zero?
- Os zeros:
  - ints: 0
  - floats: 0.0
  - booleans: false
  - strings: ""
  - pointers, functions, interfaces, slices, channels, maps: nil
- Use := sempre que possível.
- Use var para package-level scope.

### Exemplo

```
var a int
var b float64
var c string
var d bool`
 
    
    func main() {
     fmt.Printf("%v, %T\n", a, a) // -> 0, int
     fmt.Printf("%v, %T\n", b, b) // -> 0, float64
     fmt.Printf("%v, %T\n", c, c) // -> , string
     fmt.Printf("%v, %T\n", d, d) // -> false, bool
    } 
```

---

# Cap. 2 – Variáveis, Valores & Tipos – 7. O pacote fmt

## O pacote fmt

- Setup: strings, ints, bools.
- Strings: interpreted string literals vs. raw string literals.
  - Rune literals.
  - Em ciência da computação, um literal é uma notação para representar um valor fixo no código fonte.

- Format printing: documentação.
  - Grupo #1: Print -> standard out
    - func Print(a ...interface{}) (n int, err error)
    - func Println(a ...interface{}) (n int, err error)
    - func Printf(format string, a ...interface{}) (n int, err error)
      - Format verbs. (%v %T)

  - Grupo #2: Print -> string, pode ser usado como variável
    - func Sprint(a ...interface{}) string
    - func Sprintf(format string, a ...interface{}) string
    - func Sprintln(a ...interface{}) string

  - Grupo #3: Print -> file, writer interface, e.g. arquivo ou resposta de servidor
    - func Fprint(w io.Writer, a ...interface{}) (n int, err error)
    - func Fprintf(w io.Writer, format string, a ...interface{}) (n int, err error)
    - func Fprintln(w io.Writer, a ...interface{}) (n int, err error)


## 03 - Exercicios 

## 04 – Fundamentos da Programação

### Tipo booleano

- Agora vamos explorar os tipos de maneira mais detalhada. golang.org/ref/spec. A começar pelo bool.
- O tipo bool é um tipo binário, que só pode conter um dos dois valores: true e false. (Verdadeiro ou falso, sim ou não, zero ou um, etc.)
- Sempre que você ver operadores relacionais (==, <=, >=, !=, <, >), o resultado da expressão será um valor booleano.
- Booleans são fundamentais nas tomadas de decisões em lógica condicional, declarações switch, declarações if, fluxo de controle, etc.
- Na prática:
  - Zero value
  - Atribuindo um valor
  - Bool como resultado de operadores relacionais
- Go Playground: <https://play.golang.org/p/7joj615nZw>

### Como os computadores funcionam

- Isso é importante pois daqui pra frente vamos falar de ints, bytes, e etc.
- Não é necessário um conhecimento a fundo mas é importante ter uma idéia de como as coisas funcionam por trás dos panos.
- <https://docs.google.com/presentation/d/1aVytiGOBVDMISFW-ZARJ5iFY1osU2XJIw0hQpNICXm8/>
- ASCII: <https://en.wikipedia.org/wiki/ASCII>
- Filme: Alan Turing, The Immitation Game.

### Tipos numéricos

- int vs. float: Números inteiros vs. números com frações.
- golang.org/ref/spec → numeric types
- Integers:
  - Números inteiros
  - int & uint → “implementation-specific sizes”
  - Todos os tipos numéricos são distintos, exceto:
    - byte = uint8
    - rune = int32 (UTF8)
        (O código fonte da linguagem Go é sempre em UTF-8).
  - Tipos são únicos
    - Go é uma linguagem estática
    - int e int32 não são a mesma coisa
    - Para "misturá-los" é necessário conversão
  - Regra geral: use somente int
- Floating point:
  - Números racionais ou reais
  - Regra geral: use somente float64
- Na prática:
  - Defaults com :=
  - Tipagem com var
  - Dá pra colocar número com vírgula em tipo int?
  - Overflow
  - Go Playground: <https://play.golang.org/p/dt2x1ies5b>
- “implementation-specific sizes”? Runtime package. Word.
  - GOOS
  - GORUNTIME
  - <https://play.golang.org/p/1vp5DImIMM>

### Overflow

- Um uint16, por exemplo, vai de 0 a 65535.
- Que acontece se a gente tentar usar 65536?
- Ou se a gente estiver em 65535 e tentar adicionar mais 1?
- Playground: <https://play.golang.org/p/t7Z4m127F2t>

### Tipo string (cadeias de caracteres)

- Strings são sequencias de bytes.
- Imutáveis.
- Uma string é um "slice of bytes" (ou, em português, uma fatia de bytes).
- Na prática:
  - %v %T
  - Raw string literals
  - Conversão para slice of bytes: []byte(x)
  - %#U, %#x
  - Go Playground: <https://play.golang.org/p/dt2x1ies5b> & <https://play.golang.org/p/PpDnspiyA_7>
- <https://blog.golang.org/strings>

### Sistemas numéricos

- Base-10: decimal, 0–9
- Base-2: binário, 0–1
- Base-16: hexadecimal, 0–f
- <https://docs.google.com/document/d/1GqXpubhMMIr4Sy5xwgiPIDh5PGVmVpF2u0c9vDrvykE/>
- Demonstração em Go.

### Constantes

- São valores imutáveis.
- Podem ser tipadas ou não:
  - const oi = "Bom dia"
  - const oi string = "Bom dia"
- As não tipadas só terão um tipo atribuido a elas quando forem usadas.
  - Ex. qual o tipo de 42? int? uint? float64?
  - Ou seja, é uma flexibilidade conveniente.
- Na prática: int, float, string.
  - const x = y
  - const ( x = y )

### Iota

- golang.org/ref/spec
- Numa declaração de constantes, o identificador iota representa números sequenciais.
- Na prática.
  - iota, iota + 1, a = iota b c, reinicia em cada const, _
- Go Playground: <https://play.golang.org/p/eSrwoQjuYR>

### Deslocamento de bits

- Deslocamento de bits é quando deslocamos digitos binários para a esquerda ou direita.
- Na prática:
  - %d %b
  - x << y
  - iota * 10 << 10 = kb, mb, gb

- <https://play.golang.org/p/7MOnbhx4R4>
- <https://splice.com/blog/iota-elegant-constants-golang/>
- <https://medium.com/learning-the-go-programming-language/bit-hacking-with-go-e0acee258827>

- Fim da sessão. Massa!
