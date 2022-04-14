# Lista 1: Elementos fundamentais de programação em C++
<sub>Última atualização: 14/04/2022</sub>

## Visão Geral e Objetivos
O objetivo desta lista de exercícios é colocar em prática as habilidades de **interpretar especificações de problemas** e projetar e implementar uma soluções na forma de programas na linguagem de programação C++. Para tanto, esta lista explora elementos fundamentais da programação em C++, como laços, estruturas condicionais simples e compostas, tipos de dados básicos e heterogêneos expressões lógicas, passagem de parâmetros, criação de funções, leitura de escrita de informações a partir da entrada e saída padrão, dentre outros.

De forma adicional, esta lista de exercícios também aborda elementos da [*Standard Template Library* (STL)](https://en.wikipedia.org/wiki/Standard_Template_Library). A STL integra a biblioteca da linguagem de programação C++ provendo um conjunto de classes referentes a estruturas de dados comuns como vetor, lista, pilha, etc. (*containers*), bem como algoritmos e iteradores para operarem sobre tais estruturas. Pelo fato de serem classes *template*, todos esses elementos genéricos, sendo, portanto, capazes de manipular quaisquer tipos de dados.

## Tarefas
As tarefas centrais a serem realizadas neste trabalho consistem em projetar e implementar, em C++, programas para cada um dos cinco seguintes problemas:

1. negativo5
3. soma_vizinhos
4. fibonacci
5. minmax
6. inverter

A descrição de cada um desses problemas está em seu respectivo diretório, onde também deverão constar o código fonte das soluções implementadas.

## Orientações Gerais
No desenvolvimento das soluções aos problemas propostos, as seguintes observações deverão ser atendidas:

1. Apesar da completa compatibilidade entre as linguagens de programação C e C++, o código fonte produzido **não** deverá conter recursos da linguagem C nem ser resultante da mescla entre as duas linguagens, o que é uma má prática de programação. Dessa forma, deverão ser utilizados **estritamente** recursos da linguagem C++.
2. Durante a compilação do código fonte, a exibição de mensagens de aviso (*warnings*) deverá ser habilitada por meio de *flags* passadas ao compilador, uma vez que elas podem dar indícios de que o programa potencialmente possui problemas em sua implementação que podem se manifestar durante sua execução.
3. Boas práticas de programação deverão ser constantemente aplicadas. Os programas deverão ser codificados de forma legível (com indentação de código fonte, nomes consistentes, etc.) e documentados adequadamente na forma de comentários. O código fonte deverá ainda ser anotado para dar suporte à geração automática de documentação utilizando a ferramenta [Doxygen](https://www.doxygen.nl/). O documento de apoio disponível neste [link](https://drive.google.com/file/d/1YA1KxASCNY3B8APowD2V0sL-kAso9g86/view) contém algumas instruções acerca do padrão de documentação e uso do Doxygen.
4. Deve-se buscar desenvolver os programas com qualidade, garantindo que ele funcione de forma correta e eficiente. Deve-se também pensar nas possíveis entradas que poderão ser utilizadas para testar apropriadamente cada programa, além de serem tratadas adequadamente possíveis entradas consideradas inválidas.
5. Deve-se aplicar boas práticas de modularização, em termos da implementação de diferentes funções e separação entre arquivos cabeçalho (`.h`) e de corpo (`.cpp`).

## Autoria e Política de Colaboração
**Este trabalho deverá necessariamente ser realizado em equipe composta de no máximo dois integrantes**, sendo importante, dentro do possível, dividir as tarefas igualmente entre os integrantes da equipe. O trabalho em cooperação entre estudantes da mesma turma ou de outras turmas é estimulado, sendo admissível a discussão de ideias e estratégias. Contudo, tal interação não deve ser entendida como permissão para utilização de (parte de) código fonte de colegas, o que pode caracterizar situação de plágio. Trabalhos copiados no todo ou em parte de outros colegas ou da Internet serão anulados e receberão nota zero.

## Entrega
O sistema de controle de versões [Git](https://git-scm.com) e o serviço de hospedagem de repositórios [GitHub](https://git-scm.com) serão utilizados para possibilitar a entrega das implementações realizadas. Para possibilitar a associação de repositórios Git para cada equipe e reuni-los sob uma mesma infraestrutura, foi criada uma atividade (*assignment*) no [GitHub Classroom](https://classroom.github.com/classrooms). Um integrante de cada equipe deverá acessar este [link](https://classroom.github.com/a/lFZrVSk7) e aceitar o convite para ingressar na atividade. Feito isso, o próprio GitHub Classroom fará a criação de um repositório específico para a equipe em questão. Este [vídeo](https://youtu.be/ObaFRGp_Eko) demonstra como ocorre esse processo.

O repositório Git criado pelo GitHub Classroom para cada equipe segue a mesma estrutura de diretórios presentes neste repositório. Todos os arquivos deverão constar no repositório obedecendo **estritamente** a divisão em diretórios, ou seja, os códigos fonte referentes às soluções implementadas deverão estar nos respectivos diretórios de cada problema. Além disso, o arquivo `author.md` presente no repositório deverá ser editado preenchendo as informações de identificação dos integrantes da equipe e informando-se quais dos problemas foram solucionados com sucesso. A fim de garantir a boa manutenção do repositório, deve-se ainda configurar corretamente o arquivo `.gitignore` para desconsiderar arquivos que não devam ser versionados.

A implementação das soluções para os problemas propostos neste trabalho deverá ser realizada **até as 23h59 do dia 30 de abril de 2022** no respectivo repositório Git da equipe. Para fins de registro, o endereço do repositório também deverá ser enviado através da opção *Tarefas* na Turma Virtual do SIGAA. **Não serão aceitos envios por outros meios ou repositórios que não sejam os descritos nesta especificação.**

## Avaliação
A avaliação de cada uma das soluções para os problemas propostos contabilizará nota de até 2,0 pontos cada, totalizando 10,0 pontos. As soluções implementadas serão avaliadas de acordo com os seguintes critérios: 

1. utilização correta dos recursos providos pela linguagem de programação C++;
2. corretude da execução dos programas implementados, que devem apresentar saída em conformidade com a especificação e as entradas de dados fornecidas;
3. aplicação de boas práticas de programação, incluindo legibilidade, organização e documentação de código fonte, e;
4. correta utilização do repositório Git, no qual deverá ser registrado todo o histórico da implementação por meio de *commits*. 

O não cumprimento de algum dos critérios de avaliação especificados poderá resultar nos seguintes decréscimos, aplicados sobre a nota obtida até então na avaliação de cada solução:

| Falta | Decréscimo |
| :--- | ---: |
| Programa apresenta erros de compilação, não executa ou apresenta saída incorreta | -70% |
| Falta de comentários no código fonte e/ou de documentação gerada com Doxygen | -10% |
| Uso inadequado de controle de versão com Git | -20% |
| Implementação na linguagem C ou resultante de mistura entre as linguagens C e C++ | -30% |
| Programa compila com mensagens de aviso (*warnings*) | -50% |
| Plagiarismo | -100% |
