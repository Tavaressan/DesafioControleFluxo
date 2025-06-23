# DesafioControleFluxo

Desafio de Projeto do bootcamp **Santander Java 2025**: Exercício prático sobre Controle de Fluxo em Java.

## Descrição

Este projeto consiste em um sistema simples de contagem utilizando os conceitos de controle de fluxo em Java. O programa lê dois números inteiros do usuário via terminal e imprime a quantidade de interações correspondente à diferença entre os números. Caso o primeiro número seja maior que o segundo, uma exceção customizada é lançada.

> **Exemplo:**  
> Se os números informados forem `12` e `30`, o sistema irá imprimir 18 linhas, de "Imprimindo o número 1" até "Imprimindo o número 18".

---

## Requisitos do Projeto

- Receber dois parâmetros inteiros via terminal.
- Calcular a diferença entre os números e imprimir no console a contagem do 1 até o resultado.
- Se o primeiro parâmetro for maior que o segundo, lançar a exceção customizada `ParametrosInvalidosException` com a mensagem:  
  `"O segundo parâmetro deve ser maior que o primeiro"`
- Estrutura recomendada de classes:
  - `Contador.java` (classe principal)
  - `ParametrosInvalidosException.java` (classe de exceção customizada)

---

## Estrutura do Projeto
```
DesafioControleFluxo/
├── src/
│   ├── Contador.java
│   └── ParametrosInvalidosException.java
└── README.md
```

## Exemplo de Uso

```
$ java Contador
Digite o primeiro parâmetro
12
Digite o segundo parâmetro
30
Imprimindo o número 1
Imprimindo o número 2
...
Imprimindo o número 18

```

Se o primeiro parâmetro for maior que o segundo:

```
$ java Contador
Digite o primeiro parâmetro
30
Digite o segundo parâmetro
12
O segundo parâmetro deve ser maior que o primeiro
```

## Implementação

### Contador.java
```
import java.util.Scanner;

public class Contador {
    public static void main(String[] args) {
        Scanner terminal = new Scanner(System.in);
        System.out.println("Digite o primeiro parâmetro");
        int parametroUm = terminal.nextInt();
        System.out.println("Digite o segundo parâmetro");
        int parametroDois = terminal.nextInt();

        try {
            contar(parametroUm, parametroDois);
        } catch (ParametrosInvalidosException exception) {
            System.out.println("O segundo parâmetro deve ser maior que o primeiro");
        }
    }

    static void contar(int parametroUm, int parametroDois) throws ParametrosInvalidosException {
        if (parametroUm > parametroDois) {
            throw new ParametrosInvalidosException();
        }
        int contagem = parametroDois - parametroUm;
        for (int i = 1; i <= contagem; i++) {
            System.out.println("Imprimindo o número " + i);
        }
    }
}
```

### ParametrosInvalidosException.java

```
public class ParametrosInvalidosException extends Exception {
}
```

## Como executar

1. Compile as classes Java:
```
javac Contador.java ParametrosInvalidosException.java
```
2. Execute o programa:
```
java Contador
```
## Autor
Desenvolvido por [Tavaressan](https://github.com/Tavaressan) como parte do bootcamp Santander Java 2025.

