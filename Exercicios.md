# Ex.1

- Utilizando o operador curto de declaração, atribua estes valores às variáveis com os identificadores "x", "y", e "z".
    1. 42
    2. "James Bond"
    3. true
- Agora demonstre os valores nestas variáveis, com:
    1. Uma única declaração print
    2. Múltiplas declarações print

---

## Solução Ex.1 para

    func main() {
      x := 42
      y := "James Bond"
      z := true
      fmt.Println(x, y, z)
      fmt.Println(x)
      fmt.Println(y)
      fmt.Println(z)
    }

# Ex.2

- Use var para declarar três variáveis. Elas devem ter package-level scope. Não atribua valores a estas variáveis. Utilize os seguintes identificadores e tipos para estas variáveis:
    1. Identificador "x" deverá ter tipo int
    2. Identificador "y" deverá ter tipo string
    3. Identificador "z" deverá ter tipo bool
- Na função main:
    1. Demonstre os valores de cada identificador
    2. O compilador atribuiu valores para essas variáveis. Como esses valores se chamam?

---

## Solução Ex.2

    var x int
    var y string
    var z bool

    func main() {
    
     fmt.Println(x) // -> 0
     fmt.Println(y) // -> ""
     fmt.Println(z) // -> false
    }

# Ex.3

- 1. Em package-level scope, atribua os seguintes valores às variáveis:
        1. para "x" atribua 42
        2. para "y" atribua "James Bond"
        3. para "z" atribua true
    2. Na função main:
        1. Use fmt.Sprintf para atribuir todos esses valores a uma única variável. Faça essa atribuição de tipo string a uma variável utilizando o operador curto de declaração.
        2. Demonstre a variável .

## Solução Ex.3

    var x int = 42
    var y string = "texto"
    var z bool = true

    func main() {
     newString := fmt.Sprintf("%v\t%v\t%v", x, y, z)
     fmt.Println(newString) // -> "42 texto true"

    }

# Ex.4

- Crie um tipo. O tipo subjacente deve ser int.
- Crie uma variável para este tipo, com o identificador "x", utilizando a palavra-chave var.
- Na função main:
    1. Demonstre o valor da variável "x"
    2. Demonstre o tipo da variável "x"
    3. Atribua 42 à variável "x" utilizando o o operador "="
    4. Demonstre o valor da variável "x"

## Solução #Ex.4

    type newInt int

    var x newInt

    func main() {
     fmt.Printf("%T, %v\n", x, x) // -> main.newInt, 0
     x = 42
     fmt.Printf("%T, %v", x, x) // -> main.newInt, 42
    }

# Ex.5

- Utilizando a solução do exercício anterior:
    1. Em package-level scope, utilizando a palavra-chave var, crie uma variável com o identificador "y". O tipo desta variável deve ser o tipo subjacente do tipo que você criou no exercício anterior.
    2. Na função main:
        1. Isto já deve estar feito:
            1. Demonstre o valor da variável "x"
            2. Demonstre o tipo da variável "x"
            3. Atribua 42 à variável "x" utilizando o operador "="
            4. Demonstre o valor da variável "x"
        2. Agora faça tambem:
            1. Utilize conversão para transformar o tipo do valor da variável "x" em seu tipo subjacente e, utilizando o operador "=", atribua o valor de "x" a "y"
            2. Demonstre o valor de "y"
            3. Demonstre o tipo de "y"

## Solução Ex.5

    type newInt int
    var x newInt
    var y int
    
    func main() {
        fmt.Printf("%T, %v\n", x, x) // -> main.newInt, 0
        x = 42
        fmt.Printf("%T, %v\n", x, x) // -> main.newInt, 42
        y = int(x)
        fmt.Printf("%T, %v", y, y) // -> int, 42
        }

# Cap. 5

# Nível 2 – 1

    - Escreva um programa que mostre um número em decimal, binário, e hexadecimal.

## Solução Ex.1

    func main() {
     x := 100
     fmt.Printf("%d, %#x, %b", x, x, x)
    }

# Nível 2 - 2

    - Escreva expressões utilizando os operadores, e atribua seus valores a variáveis.
    - Demonstre estes valores.

## Solução Ex.2

    func main() {
     a := (10 == 100) // -> false
     b := (10 != 100) // -> true
     c := (10 <= 100) // -> true
     d := (10 < 100)  // -> true
     e := (10 >= 100) // -> false
     f := (10 > 100)  // -> false
     fmt.Printf("%v\n%v\n%v\n%v\n%v\n%v\n", a, b, c, d, e, f)
    }

# Nível 2-3

- Crie constantes tipadas e não-tipadas.
- Demonstre seus valores.

## Solução Ex.3

    const x int = 10
    const y = 10

    func main() {
     fmt.Println(x, y)
    }

# Nível 2-4

    - Crie um programa que:
    - Atribua um valor int a uma variável
    - Demonstre este valor em decimal, binário e hexadecimal
    - Desloque os bits dessa variável 1 para a esquerda, e atribua o resultado a outra variável
    - Demonstre esta outra variável em decimal, binário e hexadecimal

## Solução Ex.4

    func main() {
     x := 200
     fmt.Printf("%d\t%b\t%#x\n", x, x, x)
     y := x << 1
     fmt.Printf("%d\t%b\t%#x", y, y, y)
    }

# Nível 2-5

    - Crie uma variável de tipo string utilizando uma raw string literal.
    - Demonstre-a.

## Solução Ex.5

    func main() {
     x := `As operárias são livres
              Os zangões também voam
               Mas a rainha é escrava`
     fmt.Println(x)
    }

# Nível 2-6

    - Utilizando iota, crie 4 constantes cujos valores sejam os próximos 4 anos.
    - Demonstre estes valores.

## Solução Ex.6

    const (
     _ = 2022 + iota
     b
     c
     d
     e
    )

    func main() {
     fmt.Println(b, c, d, e)
    }
