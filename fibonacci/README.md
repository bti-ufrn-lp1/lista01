# `fibonacci`
<sup>Última atualização: 15/04/2022</sup>

Implemente uma função em C++ chamada `fib_below_n` que recebe como parâmetro um valor inteiro positivo *n* e armazena os termos da [sequência de Fibonacci](https://pt.wikipedia.org/wiki/Sequência_de_Fibonacci) inferiores a esse valor em um vetor do tipo `std::vector` contendo valores do tipo inteiro, o qual deverá ser retornado pela função. Essa função deve ter a seguinte assinatura:

```c++
std::vector<int> fib_below_n(unsigned int n);
```
A sequência de Fibonacci define-se como uma sequencia de números inteiros na qual os dois primeiros termos são iguais a 1 e cada termo seguinte é a soma dos dois termos imediatamente anteriores. Desta forma, por exemplo, se fosse fornecida uma entrada com o valor 15, o programa deveria produzir a seguinte sequência de termos da série: `{1; 1; 2; 3; 5; 8; 13}`.

## Conhecimentos Necessários
- Utilização de funcões
- Laços
- Utilização da classe [`std::vector`](https://www.cplusplus.com/reference/vector/vector/) da *Standard Template Library* (STL), representando um vetor de tamanho dinâmico.
