# `minmax`
<sup>Última atualização: 15/04/2022</sup>

Escreva uma função em C++ chamada `min_max` que recebe como parâmetro um vetor *V* com *n* números inteiros, identifica e retorna um par de valores correspondendo aos índices da primeira ocorrência do menor elemento e da última ocorrência do maior elemento presentes em *V*. Esse par será um objeto da classe utilitária [`std::pair`](https://www.cplusplus.com/reference/utility/pair/pair/).

A função deve ter a seguinte assinatura:

```c++
std::pair <size_t ,size_t> min_max (int V[], size_t n);
```

## Exemplos de Entrada/Saída
Entrada | Saída
:---------- | :-----
{5, 4, 1, 3, 1, 10, 7, 10, 6, 8} | `{2, 7}` (posição `2` do primeiro 1, posição `7` do último 10)
{8, 12, 12, 5, 9, 2, 2, 4, 6, 8} | `{5, 2}` (posição `5` do primeiro 2, posição `2` do último 12)

## Conhecimentos Necessários
- Função
- Passagem de vetor por parâmetro
- Estruturas condicionais
- Laços
- Classe [`std::pair`](https://www.cplusplus.com/reference/utility/pair/pair/), definida na biblioteca [`utility`](https://www.cplusplus.com/reference/utility/)
- Retorno de funçao com tipo composto
