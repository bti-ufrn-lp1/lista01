# `inverter`
<sup>Última atualização: 15/04/2022</sup>

Escreva uma função em C++ chamada `reverse` que recebe como parâmetro uma referência para um vetor estático de *strings*, implementado por meio da classe [`std::array`](https://www.cplusplus.com/reference/array/array/) da *Standard Template Library* (STL), e inverte a ordem dos seus elementos da forma mais eficiente possível. Essa função deve ter a seguinte assinatura:

```c++
template <size_t SIZE>
void reverse(std::array <std::string, SIZE> &arr);
```

Note-se nessa assinatura a presenta da palavra-chave `template`. Essa construção permite que a variável `SIZE`, um valor inteiro longo sem sinal, seja definida em tempo de compilação por quem invocar sua função. Uma das vantagens de usar uma classe para definir o vetor é que a classe `std::array` 
possui várias funcionalidades já implementadas e disponíveis para uso. Por exemplo, caso deseje-se recuperar a quantidade de elementos em `arr`, basta invocar o método `size`, sem a necessidade de informar à função o número de elementos:

```c++
size_t tamanho = arr.size();
```

Outro ponto a se observar é uso do operador de referncia `&` associado ao parâmetro `arr`. Essa construção faz com que a função receba uma *referencia* para a variável que é passada no parâmetro quando a função é usada, fazendo com que operações em `arr` sejam refletidas fora do escopo da função quando ela termina. Em razão disso, o retorno da função é `void`, e não o vetor na ordem reversa.

Da mesma forma na linguagem C, em C++, quando funções recebem vetores básicos (conhecidos como *raw arrays*, os quais utilizam o operador `[``]`), a função sempre recebe uma referencia, implicando que mudanças no vetor são refletidas fora do escopo da função. No entanto, a função `reverse` aqui implementada utiliza um objeto do tipo `std::array`; neste caso, por padrão, a **passagem de parâmetro é por valor**, implicando que mudanças no vetor recebido não são refletidas quando a função termina. Para mudar esse comportamento, é utilizado o operador `&` na frente do parâmetro desejado, fazendo com que a passagem de parâmetro seja **por referência**.

**Observação**: Não é necessário criar um outro vetor para inverter os valores presentes no vetor passado por referência. A inversão pode ser feita internamente, ou seja, dentro do próprio vetor, com a ajuda de variáveis auxiliares.

## Exemplos de Entrada/Saída
Por exemplo, considere o vetor A contém as seguintes strings: \["um", "dois", "três", "quatro"\], após a execução
da função o vetor A deverá ter seus elementos na seguinte ordem: \["quatro", "três", "dois", "um"\].

## Conhecimentos Necessários
- Funções
- Laços
- Strings
- Passagem de parâmetro por referência
- Classe [`std::array`](https://www.cplusplus.com/reference/array/array/) da *Standard Template Library* (STL), representando um vetor estático de tamanho fixo
- Método [`std::swap`](https://www.cplusplus.com/reference/utility/swap/) definido na biblioteca [`utility`](https://www.cplusplus.com/reference/utility/).


