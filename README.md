# HDL Judge

## Motivação e Objetivo

Nos cursos de computação há disciplinas onde são ensinados tópicos base da área de computação, abordando principalmente lógica computacional e como são projetados os circuitos lógicos. Muitos destes conceitos são ensinados através de HDLs (Hardware Description Languages), que são linguagens que definem o comportamento de circuitos lógicos. Apesar de as HDLs serem importante para o entendimento e aplicação de conceitos da área de computação, as ferramentas que permitem trabalhar com elas são desenhadas para a indústria, sendo em sua maioria complexas e pesadas.

Em face deste cenário, a motivação para este trabalho é facilitar o processo de aprendizagem e execução das HDLs, tornando possível que os alunos comecem a programar e aprender na prática o mais rápido possível e com o mínimo de dificuldade, de forma que possam focar no aprendizado do conteúdo em si e não na configuração e utilização de diversas ferramentas.

O objetivo deste projeto é o desenvolvimento de um sistema de simulação de hardware na web para auxiliar no aprendizado de desenvolvimento de hardware nas disciplinas de graduação. Para o aluno, o projeto é uma ferramenta única de fácil operação para a elaboração de códigos, criação de testes e análise de comportamento dos componentes criados. Já para os professores, a ferramenta permite acompanhar o desempenho e avaliar com rapidez os projetos dos alunos.

## Especificação

Inicialmente para compreender o escopo do projeto, foram analisadas diversas ferramentas para testes e desenvolvimento de códigos em VHDL, além de soluções para gerenciamento de exercícios acadêmicos. Para cada solução foram elencados os pontos positivos e negativos, a fim de avaliar quais poderiam ser utilizadas no projeto.

A partir do estudo das soluções e do contexto acadêmico de uso destas ferramentas, foi possível definir dois tipos de usuários principais da aplicação: aluno e professor, em que para cada um foram descritas as jornadas de uso da aplicação (Figura 1). Com base na jornada dos principais usuários, foi possível elaborar requisitos funcionais e não funcionais para a aplicação.

## Arquitetura

A arquitetura do projeto consiste de um frontend desenvolvido com Svelte, que se comunica com uma API escrita em Python com a biblioteca FastAPI (Figura 2). O projeto utiliza a Arquitetura Hexagonal, onde a API aciona classes chamadas de controllers, que contém as regras de negócio e que se comunicam com serviços externos através de adapters. Os adapters podem ser trocados para permitir a adição de novas funcionalidades, como adição de outras HDLs e de outros serviços de detecção de plágio.

Para executar os testes de VHDL foi utilizado o simulador open-source GHDL, como banco de dados foi utilizado o SQLite e para realizar verificação de plágio foi realizada a integração com o serviço Moss da Universidade de Stanford.

## Resultado

A aplicação desenvolvida foi validada utilizando como caso de uso um projeto semelhante ao aplicado nas disciplinas da Escola Politécnica, onde os alunos devem implementar e testar uma memória cache. Para tanto, seguiu-se as jornadas para cada tipo de usuário, verificando as funcionalidades de cada passo.

Verificou-se que a aplicação foi capaz de atingir os requisitos de funcionalidades para os dois tipos de usuário, sendo possível realizar todas os passos das jornadas definidas. Além disso, a aplicação apresenta uma arquitetura robusta, segura, adaptável e escalável, cumprindo as necessidades do sistema, além de permitir a adição de novos componentes no futuro.

Possíveis pontos de continuidade e de melhoria no trabalho foram detectados, como uma melhor integração com visualizador de forma de onda, mais opções de gerenciamento das turmas e dos exercícios a serem feitos, além da adição de suporte a linguagem Verilog. Estas modificações podem ser feitas por qualquer pessoa, uma vez que o código do projeto será disponibilizado para livre uso na internet.
