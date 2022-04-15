# `fibonacci`
<sup>Última atualização: 15/04/2022</sup>

Implemente uma função em C++ chamada `fib_below_n` que recebe como parâmetro um valor inteiro positivo *n* e armazena os termos da [sequência de Fibonacci](https://pt.wikipedia.org/wiki/Sequência_de_Fibonacci) inferiores a esse valor em um vetor do tipo `std::vector` contendo valores do tipo inteiro, o qual deverá ser retornado pela função. Essa função deve ter a seguinte assinatura:

```c++
std::vector<int> fib_below_n(unsigned int n);
```

## Exemplos de Entrada/Saída
Entrada | Saída
---- | :-----
7 | `{1; 1; 2; 3; 5}`
15 | `{1; 1; 2; 3; 5; 8; 13}`
21 | `{1; 1; 2; 3; 5; 8; 13}`

## Conhecimentos Necessários
- Funções
- Laços
- Classe [`std::vector`](https://www.cplusplus.com/reference/vector/vector/) da *Standard Template Library* (STL), representando um vetor de tamanho dinâmico.
