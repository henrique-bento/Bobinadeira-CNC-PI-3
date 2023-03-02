# Bobinadeira e CNC com controle de 3 eixos PI-3

## 1. Sensores indutivos para Industria 

Os sensores indutivos são uma das partes mais importantes em vários equipamentos pois eles ditam qual sera a precisão da medida. Eles são basicamente bobinas que são encarregadas de gerar campos eletromagnéticos, esses campos que são gerados por esses sensores e sua forma são o que ditam a qualidade da funcionamento e quais os limites que podem ser impostos ao equipamento. Esses sensores tem uma serie de especificações de confecção como largura, comprimento, numero de espiras e distancia entre as mesmas então garantir a sua precisão de confecção é algo de suma importância para não se ter problemas na hora de construir o equipamento e realizar a configuração.

## 2. Protótipo do Projeto desenvolvido anteriormente

O projeto dessa maquina foi desenvolvido anteriormente como um protótipo onde se tinha a ideia de desenvolver uma maquina que confeccionasse esses sensores de equipamentos voltados para a area industrial onde atuo como desenvolvedor. Esses sensores tem características muito especificas essas características são essenciais para o funcionamento adequado, tendo isso em mente esse trabalho sendo realizado por humanos estava muito mais sucessível a erros então a implementação de uma maquina que não erre essas características seria uma grande vantagem para a produção dos equipamentos. Então o desenvolvimento do projeto se iniciou e como o local onde os sensores ficam são laterais planas se pensou na estrutura de uma CNC Router como base para o desenvolvimento dessa maquina, foi cogitada a possibilidade de se usar o software de uma CNC open-source para se projetar desenhos e assim reduzir os trabalhos em cima de software porem com o numero alto de especificações na confecção que levam a uma alta necessidade de controle do movimento foi então definido que seria desenvolvido um código proprietário. Basicamente o funcionamento dessa maquina consiste em ter um bico que traciona um fio de metal que passa por uma chapa de madeira que possui pinos pré fixados e essa se utilizando de seus 3 eixos executa a ordem correta de confecção dos sensores tendo em vista o largura e comprimento e numero de espiras do sensor e também o sentido da espira. Atualmente são feitos dois tipos de sensores com as suas respectivas especificações. Como IHM essa maquina usa um display com comunicação serial nele e possível selecionar qual tipo de sensor sera feito e como esta o progresso do mesmo. Após a implementação da confecção dos sensores também foi feita uma adição de uma o rotina de furos e cortes em chapa de madeira fazendo a troca do bico de tração de fio por um spindle de CNC, com essa nova funcionalidade e feito os furos dos pinos de fixação dos sensores que vão no equipamento e cortes de fixação. Todas essas rotinas de movimentação foram feitas por um código proprietário que controla cada movimento da maquina mas como esse protótipo foi desenvolvido com uma plataforma não profissional ele possui limitações de velocidade de controle dos motores, problemas com aquecimento e o software precisa de correções e novas implementações para possibilitar ajustes de desenho sem precisar alterar o software como um todo e deixando a bobinadeira completamente stand alone. 

## 3. Proposta  
Utilizando de conceitos e aprendizados provenientes do curso de engenharia eletrônica, foi definido como projeto a elaboração de uma maquina para fabricação de bobinas para a industria em geral. A realização e o desenvolvimento da proposta será feita de acordo com a metodologia orientada à projetos denominada “Abordagem CDIO”, composta de 4 etapas: Concepção, Design, Implementação e Operação. A descrição de cada etapa será contextualizada no decorrer do trabalho.

## 4. Concepção

A bobinadeira e uma ferramenta utilizada no chão de fabrica e busca agilizar a produção da melhor maneira possível e com o menor auxilio possível de um colaborador, podendo assim reduzir o tempo de confecção dos sensores com a melhor precisão e qualidade de confecção.Seguindo esse pensamento, nesta etapa nós desenvolvedores devemos nos apropriar do contexto, definir os requisitos e meios para alcançar nossos objetivos, sendo estes:

* Realimentação de posição inicial;
  O sistema de controle de posição inicial serve para a maquina ter um controle da posição de inicio de trajeto, esse processo sera feito toda vez que uma operação for realizada cada eixo tera um sensor indutivo que indicara a posição zero de cada eixo.

* Sistema de controle de posição em caso de emergência;
  O sistema de controle em caso de erro de trajeto que causa uma pausa de emergência sera feito no extremos de cada eixo e sera feito com chaves fim de curso mecânicas.

* Controle de cargas, visando redução de detritos e controle do spindle;
 O controle de cargas se refere a controle de reles que são acionados com sinais de até 5V que podem acionar diferentes tipos de cargas, algumas propostas são um sistema de aspiração de detritos e o spindle se usada a opção de furação.

* Sinalização auditiva/visual de processo concluído;
  A sinalização auditiva e visual serve para sinalização e enformar a finalização de processo e assim feito a preparação para a nova operação. Como se trata de uma maquina destinada para chão de fabrica a sinalização visual a tecnologia escolhida e uma torre de sinalização industrial que contem tanto sinal auditivo como visual e possui um acionamento de 220V.

* Sistema de parada de emergência;
  O sistema de parada de emergência consistira em botões retentores que irão paralisar o processo que esta sendo executado e o processo só voltara a executar assim que o botão for desativado, esse sistema trás a possibilidade de se fazer algum ajuste mecânico para não se perder o processo ou aconteça algo que possa causar um acidente.

* IHM resistente ao chão de fabrica e que possa ser usada com luvas;
  A interface homem maquina e de suma importância para o controle da mesma sera realizado com um display com comunicação serial touch screen com característica resistiva assim pode ser operado com luvas e tendo uma melhor resistência a variação de temperatura.

* Central para visualização de medidas dos sensores;
  Esse sistema sera implementado através de softwares e sera uma pagina que ira exibir as características dos sensores indutivos e como sera sua confecção possibilitando assim averiguar se as medidas do processo estão de acordo com o projeto inicial.

* Entrada e alteração das medidas dos sensores;
  A entrada e alteração dos valores dos sensores e um funcionalidade muito util para possibilitar que pequenos ajustes sejam feitos ou até mesmo uma mudança de projeto maior seja implementada sem que o programa da maquina tenha que ser atualizado assim deixando o equipamento mais independente e de fácil manuseio e atualização.

* Precisão de movimento com uma velocidade adequada;
  Atualmente com o microcontrolador utilizado um Atmega 2560 que esta numa plataforma Arduíno se tem uma limitação de velocidade de passo e precisão pelo clock reduzido da mesmo sendo somente de 16 MHz, para se retirar essa limitação e fazer a versão final que consegue extrair a velocidade máxima e ideal dos motores o microcontrolador que pode ser utilizado nesse caso pode ser um ESP32 que por exemplo tem disponível um clock de ate 240 Mhz outra possibilidade é um microcontrolador da família STM32 que também possua a especificação adequada onde a disponibilidade ,preço e acesso a informação ira selecionar qual a melhor escolha.

Abaixo é apresentado o diagrama de blocos que resumem de uma maneira visual a concepção de funcionamento do projeto que possibilita a partir dos requisitos acima selecionar como cada requisito sera atendido.
![Diagrama de blocos PI3](https://raw.githubusercontent.com/henrique-bento/Bobinadeira-CNC-PI-3/main/img_PI3/diagrama%20de%20blocos%20PI3.jpg)
