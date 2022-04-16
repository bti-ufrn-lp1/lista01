# Lista 1: Elementos fundamentais de programação em C++
<sub>Última atualização: 15/04/2022</sub>

## Sumário
- [Visão geral e objetivos](#visão-geral-e-objetivos)  
- [Tarefas](#tarefas)
- [Requisitos](#requisitos)
- [Categorias de exercícios](#categorias-de-exercícios)
  - [Implementação de programa](#implementação-de-programa)
  - [Implementação de função](#implementação-de-função)
- [Orientações gerais](#orientações-gerais)
- [Autoria e política de colaboração](#autoria-e-política-de-colaboração)
- [Entrega](#entrega)
- [Avaliação](#avaliação)
- [Dúvidas e informações](#dúvidas-e-informações)

## Visão geral e objetivos
O objetivo desta lista de exercícios é colocar em prática as habilidades de **interpretar especificações de problemas** e projetar e implementar uma soluções na forma de programas na linguagem de programação C++. Para tanto, esta lista explora elementos fundamentais da programação em C++, como laços, estruturas condicionais simples e compostas, tipos de dados básicos e heterogêneos expressões lógicas, passagem de parâmetros, criação de funções, leitura de escrita de informações a partir da entrada e saída padrão, dentre outros.

De forma adicional, esta lista de exercícios também aborda elementos da [*Standard Template Library* (STL)](https://en.wikipedia.org/wiki/Standard_Template_Library). A STL integra a biblioteca da linguagem de programação C++ provendo um conjunto de classes referentes a estruturas de dados comuns como vetor, lista, pilha, etc. (*containers*), bem como algoritmos e iteradores para operarem sobre tais estruturas. Todos esses elementos são genéricos, sendo, portanto, capazes de lidar com quaisquer tipos de dados.

## Tarefas
As tarefas centrais a serem realizadas neste trabalho consistem em projetar e implementar, em C++, programas para cada um dos cinco seguintes problemas:

1. [negativo5](https://github.com/bti-ufrn-lp1/lista01/tree/master/negativo5)
2. [soma_vizinhos](https://github.com/bti-ufrn-lp1/lista01/tree/master/soma_vizinhos)
3. [fibonacci](https://github.com/bti-ufrn-lp1/lista01/tree/master/fibonacci)
4. [minmax](https://github.com/bti-ufrn-lp1/lista01/tree/master/minmax)
5. [inverter](https://github.com/bti-ufrn-lp1/lista01/tree/master/inverter)

A descrição de cada um desses problemas está em seu respectivo diretório, juntamente com exemplos de entradas e saídas esperados para o programa e uma relação dos recursos da linguagem de programação C++ necessários à implementação da solução. Cada um desses repositórios possui um código fonte base que poderá ser utilizado como ponto de partida para a implementação das soluções, havendo comentários na forma de `// TODO` apontando as alterações necessárias a fazer e onde elas devem ser feitas. Dessa forma, o código fonte das soluções implementadas deverá constar nos respectivos diretórios.

Cada projeto já está preparado para ser compilado individualmente com o uso de `cmake`. Para que seja possível usufruir da infraestrutura de compilação e teste disponível, **não se deve alterar outros arquivos que não sejam aqueles indicados**. De maneira geral, é importante seguir à risca as instruções sobre a implementação dos exercícios, uma vez que as respostas serão validadas de forma automatizada. Preferencialmente, não se deve realizar qualquer modificação nos testes automatizados, a memos que seja acordado com o docente.

Por fim, caso se deseje criar outros arquivos fonte para melhor modularizar o programa, é necessário alterar o *script* do `cmake` corespondente para incluir o novo arquivo fonte na lista de dependências do alvo `${APP_NAME}` com o comando `target_sources(${APP_NAME} PRIVATE "nome_arquivo.cpp")`.

## Requisitos
Para que seja possível compilar e executar os testes preparados para este trabalho, é necessário que os seguintes elementos estejam instalados no ambiente de desenvolvimento:

- [Git](https://git-scm.com), como sistema de controle de versões
- [*GNU Compiler Collection*](https://gcc.gnu.org) (a qual inclui o compilador `g++`), [`clang`](https://clang.llvm.org/) ou qualquer outro compilador para a linguagem C++
- [`cmake`](https://cmake.org/), para gerar *makefiles* automaticamente e de forma otimizada para o projeto
- [Python 3+](https://www.python.org/), para executar o *script* de teste de comparação de saída gerada/esperada

## Categorias de exercícios
Existem duas categorias de exercícios neste trabalho: implementação de **programa** e implementação de **função**. Cada uma dessas categorias requer tarefas de implementação, compilação e testes específicas, as quais são descritas a seguir.

### Implementação de programa
Para os exercícios que solicitam a implementação de um programa, apenas o arquivo `src/main.cpp` deverá ser editado. Neste caso, deve-se assumir que os dados de entrada para cada programa são lidos a partir da entrada padrão, utilizando o operador de extração `>>` sobre o objeto `cin`, enquanto que os dados de saída devem ser enviados para a saída padrão, utilizando o operador de inserção `<<` sobre o objeto `cout`, como mostra o exemplo abaixo. Ambos os objetos são disponibilizados pela biblioteca de entrada/saída [`iostream`](https://www.cplusplus.com/reference/iostream/), integrante da linguagem C++.

```c++
int x;
std::cin >> x;                // equivalente a scanf("%d", &x) em C
std::cout << x << std::endl;  // equivalente a scanf("%d\n", x) em C
```

A título de exemplo, considere-se o projeto [`negativo5`](https://github.com/bti-ufrn-lp1/lista01/tree/master/negativo5), o qual requer a implementação de um programa. O diretório desse projeto, assim como para qualquer outro que requer a implementação de um programa como solução, deverá estar organizado da seguinte forma:

```
+─negativo5           ---> Nome do diretório do projeto
  ├─── CMakeLists.txt ---> Script de configuração do cmake
  ├─── build          ---> Diretório onde os arquivos executáveis serão gerados
  ├─── data_expected  ---> Diretório que contém os arquivos de saída com as respostas corretas
  ├─── data_in        ---> Diretório que contém os arquivos de entrada para os testes
  └─── src            ---> Diretório que contém o arquivo fonte a ser editado
       └─── main.cpp  ---> Arquivo fonte que precisa ser alterado para conter a solução
```

1. Após editar o arquivo `src/main.cpp` para implementar a solução para o problema, estando no diretório do projeto, deve-se executar os seguintes comandos:

```bash
# Criar o diretório build dentro do diretório do projeto
mkdir build

# Navegar para o diretório build criado
cd build
```

2. Em seguida, deve-se executar o seguinte comando para gerar os arquivos intermediários no diretório `build` e o *makefile*:

```bash
cmake ..
```

O resultado da execução desses comandos mostrado no terminal seria similar a:

```
$ cd negativo5
$ mkdir build
$ cd build
$ cmake ..
-- The CXX compiler identification is AppleClang 11.0.0.11000033
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /Library/Developer/CommandLineTools/usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done
-- Generating done
-- Build files have been written to: .../negativo5/build
```

3. Como próximo passo, deve-se executar o comando abaixo para compilar o projeto em questão, o qual criará um arquivo executável dentro do diretório `build` com o nome (genérico) `program`:

```bash
cmake --build .
```

Um possível resultado da execução desse comando, mostrado no terminal, seria similar a:

```
$ cmake --build .
[ 50%] Building CXX object CMakeFiles/program.dir/src/main.cpp.o
[100%] Linking CXX executable program
[100%] Built target program
```

```bash
./program
```

4. Caso haja erro de compilação, este deve ser corrigido e retorna-se ao passo 3. Caso a compilação seja bem-sucedida, o arquivo executável referente ao programa gerado dentro do diretório `build` pode ser executado através do seguinte comando no terminal:

```bash
cmake --build .
```

5. Para executar os testes automatizados (caso a compilação tenha sido bem-sucedida e o programa executável tenha sido gerado corretamente), deve-se executar o seguinte comando dentro do diretório `build`:

```bash
cmake --build . --target verify
```

6. Ao observar os resultados dos testes, caso haja alguma falha, deve-se corrigir o problema e compilar o projeto novamente conforme descrito no passo 3. Caso os testes sejam bem-sucedidos, um possível resultado da execução, mostrado no terminal, seria similar a:

```
$ cmake --build . --target verify
Consolidate compiler generated dependencies of target program
[100%] Built target program

>>> RODANDO TESTES DE COMPARAÇÃO DE ENTRADA/SAÍDA ESPERADAS <<< 

[test 01: all-negatives]: OK
[test 02: 4-negatives]: OK
[test 03: all-zeros]: OK
[test 04: no-negatives]: OK
[test 05: 2-negatives]: OK

Sumário dos testes:
• Falhas........: 0
• Erros E/S.....: 0
• Erros Execução: 0
• Sucessos......: 5

>>> TESTE CONCLUÍDO COM SUCESSO! <<< 
[100%] Built target verify
```

### Implementação de função
Para os exercícios que solicitam a implementação de uma função, é necessário alterar apenas o arquivo `src/function.cpp`. Esse arquivo contém o corpo vazio da função que precisa ser implementada. Neste caso, **não se deve alterar a assinatura da função**, pois, se isso ocorrer, os testes automatizados não funcionarão.

A título de exemplo, considere-se o projeto [`fibonacci`](https://github.com/bti-ufrn-lp1/lista01/tree/master/fibonacci), o qual requer a implementação de uma função. O diretório desse projeto, assim como para qualquer outro que requer a implementação de uma função como solução, deverá estar organizado da seguinte forma:

```
+─fibonacci               ---> Nome do diretório do projeto
  ├─── CMakeLists.txt     ---> Script de configuração do cmake
  ├─── build              ---> Diretório onde os arquivos executáveis serão gerados
  |─── tests              ---> Diretório que contém arquivos para teste unitário
  └─── src                ---> Diretório que contém o arquivo fonte a ser editado
       └─── function.h    ---> Arquivo de cabeçalho com a definição da assinatura da função
       └─── function.cpp  ---> Arquivo fonte que precisa ser alterado para conter a solução
```

1. Após editar o arquivo `src/function.cpp` para implementar a solução para o problema, estando no diretório do projeto, deve-se executar os seguintes comandos:

```bash
# Criar o diretório build dentro do diretório do projeto
mkdir build

# Navegar para o diretório build criado
cd build
```

2. Como próximo passo, deve-se executar o seguinte comando para gerar os arquivos intermediários no diretório `build` e o *makefile*:

```bash
cmake ..
```

O resultado da execução desses comandos mostrado no terminal seria similar a:

```
$ cd fibonacci
$ mkdir build
$ cd build
$ cmake ..
-- The CXX compiler identification is AppleClang 11.0.0.11000033
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /Library/Developer/CommandLineTools/usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done
-- Generating done
-- Build files have been written to: .../fibonacci/build
```

3. Em seguida, deve-se executar o seguinte comando para compilar o projeto dentro diretório `build`, o qual criará nesse diretório uma biblioteca estática contendo a função implementada, `libfunc.a`, e um arquivo executável para executar os testes unitários, `tests/all_tests`:

```bash
cmake --build .
```

Um possível resultado da execução desse comando, mostrado no terminal, seria:

```
$ cmake --build .
Scanning dependencies of target func
[ 20%] Building CXX object CMakeFiles/func.dir/src/function.cpp.o
[ 40%] Linking CXX static library libfunc.a
[ 40%] Built target func
Scanning dependencies of target all_tests
[ 60%] Building CXX object tests/CMakeFiles/all_tests.dir/main.cpp.o

[ 80%] Building CXX object tests/CMakeFiles/all_tests.dir/test_01.cpp.o
[100%] Linking CXX executable all_tests
[100%] Built target all_tests
```

4. Caso haja erro de compilação, este deve ser corrigido e retorna-se ao passo 3. Caso a compilação seja bem-sucedida, deve-se executar o seguinte comando para navegar para o diretório `build` e executar os testes:

```bash
cd build
cmake --build . --target run_tests
```

5. Ao observar os resultados dos testes, caso haja alguma falha, deve-se corrigir o problema e compilar o projeto novamente, conforme descrito no passo 3. Caso os testes sejam bem-sucedidos, um possível resultado da execução, mostrado no terminal, seria similar a:

```
$ cd build
$ cmake --build . --target run_tests
[ 40%] Built target func
[100%] Built target all_tests
===============================================================
All tests passed (16 assertions in 5 test cases)

[100%] Built target run_tests
```

## Orientações gerais
No desenvolvimento das soluções aos problemas propostos, as seguintes observações deverão ser atendidas:

1. Apesar da completa compatibilidade entre as linguagens de programação C e C++, o código fonte produzido **não** deverá conter recursos da linguagem C nem ser resultante da mescla entre as duas linguagens. Dessa forma, deverão ser utilizados **estritamente** recursos da linguagem C++.
2. Durante a compilação do código fonte, a exibição de mensagens de aviso (*warnings*) deverá ser habilitada por meio de *flags* passadas ao compilador, uma vez que elas podem dar indícios de que o programa potencialmente possui problemas em sua implementação que podem se manifestar durante sua execução.
3. Boas práticas de programação deverão ser constantemente aplicadas. Os programas deverão ser codificados de forma legível (com indentação de código fonte, nomes consistentes, etc.) e documentados adequadamente na forma de comentários. O código fonte deverá ainda ser anotado para dar suporte à geração automática de documentação utilizando a ferramenta [Doxygen](https://www.doxygen.nl/). O documento de apoio disponível neste [link](https://drive.google.com/file/d/1YA1KxASCNY3B8APowD2V0sL-kAso9g86/view) contém algumas instruções acerca do padrão de documentação e uso do Doxygen.
4. As soluções deverão ser desenvolvidas com qualidade, garantindo que o programa funcione de forma correta e eficiente. Deve-se também pensar nas possíveis entradas que poderão ser utilizadas para testar apropriadamente cada programa, além de serem tratadas adequadamente possíveis entradas consideradas inválidas.

## Autoria e política de colaboração
**Este trabalho deverá necessariamente ser realizado em equipe composta de dois estudantes**, sendo importante, dentro do possível, dividir as tarefas igualmente entre os integrantes da equipe. Após a implementação das soluções para os problemas propostos, o arquivo [`author.md`](https://github.com/bti-ufrn-lp1/lista01/blob/master/author.md) presente no repositório deverá ser editado preenchendo as informações de identificação dos integrantes da equipe, na seção [Informações de Autoria](https://github.com/bti-ufrn-lp1/lista01/blob/master/author.md#identificação-de-autoria) e informando-se quais dos problemas foram solucionados com sucesso, na seção [Soluções Implementadas](https://github.com/bti-ufrn-lp1/lista01/blob/master/author.md#soluções-implementadas). 

O trabalho em cooperação entre estudantes da mesma turma ou de outras turmas é estimulado, sendo admissível a discussão de ideias e estratégias. Contudo, tal interação não deve ser entendida como permissão para utilização de (parte de) código fonte de colegas, o que pode caracterizar situação de plágio. Trabalhos copiados no todo ou em parte de outros colegas ou da Internet serão anulados e receberão nota zero.

## Entrega
O sistema de controle de versões [Git](https://git-scm.com) e o serviço de hospedagem de repositórios [GitHub](https://git-scm.com) serão utilizados para possibilitar a entrega das implementações realizadas. Para possibilitar a associação de repositórios Git para cada equipe e reuni-los sob uma mesma infraestrutura, foi criada uma atividade (*assignment*) no GitHub Classroom. Um integrante de cada equipe deverá acessar este [*link*](https://classroom.github.com/a/lFZrVSk7) e aceitar o convite para ingressar no GitHub Classroom. Uma vez aceito o convite, será exibida a atividade referente a ester trabalho e o próprio GitHub Classroom fará a criação de um repositório específico para a equipe em questão. Este [vídeo](https://youtu.be/ObaFRGp_Eko) demonstra como ocorre esse processo.

O repositório Git criado pelo GitHub Classroom para cada equipe segue a mesma estrutura de diretórios presentes neste repositório. Todos os arquivos deverão constar no repositório obedecendo **estritamente** a divisão em diretórios, ou seja, os códigos fonte referentes às soluções implementadas deverão estar nos respectivos diretórios de cada problema. A fim de garantir a boa manutenção do repositório, deve-se ainda configurar corretamente o arquivo `.gitignore` para desconsiderar arquivos que não devam ser versionados.

A implementação das soluções para os problemas propostos neste trabalho deverá ser realizada **até as 23h59 do dia 30 de abril de 2022** no respectivo repositório Git da equipe. Para fins de registro, o endereço do repositório também deverá ser enviado através da opção *Tarefas* na Turma Virtual do SIGAA. **Não serão aceitos envios por outros meios ou repositórios que não sejam os descritos nesta especificação.**

## Avaliação
A avaliação de cada uma das soluções para os cinco problemas propostos contabilizará nota de até 2,0 pontos cada, totalizando 10,0 pontos. As soluções implementadas serão avaliadas de acordo com os seguintes critérios: 

- utilização correta dos recursos providos pela linguagem de programação C++;
- corretude da execução dos programas implementados, que devem apresentar saída em conformidade com a especificação e as entradas de dados fornecidas;
- aplicação de boas práticas de programação, incluindo legibilidade, organização e documentação de código fonte, e;
- correta utilização do repositório Git, no qual deverá ser registrado todo o histórico da implementação por meio de *commits*. 

O não cumprimento de algum dos critérios de avaliação especificados poderá resultar nos seguintes decréscimos, aplicados sobre a nota obtida até então na avaliação de cada solução:

| Falta | Decréscimo |
| :--- | ---: |
| Programa apresenta erros de compilação, não executa ou apresenta saída incorreta | -70% |
| Falta de comentários no código fonte e/ou de documentação gerada com Doxygen | -10% |
| Uso inadequado de controle de versão com Git | -20% |
| Implementação na linguagem C ou resultante de mistura entre as linguagens C e C++ | -30% |
| Programa compila com mensagens de aviso (*warnings*) | -50% |
| Plagiarismo | -100% |

## Dúvidas e informações
Caso haja qualquer dúvida, questionamento ou necessidade de informação adicional, é possível:
- enviar *e-mail* para o endereço everton.cavalcante@ufrn.br;
- enviar mensagem privada diretamente ao docente, utilizando o servidor Discord;
- enviar mensagem no canal de texto `#geral-dim0120-t02`, especificamente associado à turma no servidor Discord;
- enviar mensagem no canal de texto `#duvidas` no servidor Discord, comum a todas as turmas da disciplina;
- realizar encontros síncronos presenciais, no horário e local de aula;
- agendar encontros síncronos por videoconferência, ou;
- agendar encontros síncronos pelo canal de áudio `Fale com Prof. Everton` no servidor Discord.
