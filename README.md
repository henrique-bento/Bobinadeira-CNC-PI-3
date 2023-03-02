# Bobinadeira e CNC com controle de 3 eixos PI-3

## 1. Sensores para Industria de detectores de metais

Os sensores em um detector de metais são uma das partes mais importantes desse equipamento pois eles ditam qual sera a precisão da medida. Eles são basicamente bobinas que são encarregadas de gerar campos eletromagnéticos, esses campos que são gerados por esses sensores e sua forma são o que ditam a qualidade da detecção e quais os objetos que podem ser detectados ou não. Esses sensores tem uma serie de especificações de confecção como largura, comprimento, numero de espiras e distancia entre as mesmas então garantir a sua precisão de confecção é algo de suma importância para não se ter problemas na hora de construir o equipamento e realizar a configuração.

## 2. Protótipo do Projeto desenvolvido anteriormente

O projeto dessa maquina foi desenvolvido anteriormente como um protótipo onde se tinha a ideia de desenvolver uma maquina que confeccionasse esses sensores de equipamentos voltados para a area de detectores de metais onde atuo como desenvolvedor. Esses sensores tem características muito especificas essas características são essenciais para o funcionamento adequado, tendo isso em mente esse trabalho sendo realizado por humanos estava muito mais sucessível a erros então a implementação de uma maquina que não erre essas características seria uma grande vantagem para a produção dos equipamentos. Então o desenvolvimento do projeto se iniciou e como o local onde os sensores ficam são laterais planas se pensou na estrutura de uma CNC Router como base para o desenvolvimento dessa maquina, foi cogitada a possibilidade de se usar o software de uma CNC open-source para se projetar desenhos e assim reduzir os trabalhos em cima de software porem com o numero alto de especificações na confecção que levam a uma alta necessidade de controle do movimento foi então definido que seria desenvolvido um código proprietário. Basicamente o funcionamento dessa maquina consiste em ter um bico que traciona um fio de metal que passa por uma chapa de madeira que possui pinos pré fixados e essa se utilizando de seus 3 eixos executa a ordem correta de confecção dos sensores tendo em vista o largura e comprimento e numero de espiras do sensor e também o sentido da espira. Atualmente são feitos dois tipos de sensores com as suas respectivas especificações. Como IHM essa maquina usa um display com comunicação serial nele e possível selecionar qual tipo de sensor sera feito e como esta o progresso do mesmo. Após a implementação da confecção dos sensores também foi feita uma adição de uma o rotina de furos e cortes em chapa de madeira fazendo a troca do bico de tração de fio por um spindle de CNC, com essa nova funcionalidade e feito os furos dos pinos de fixação dos sensores que vão no equipamento e cortes de fixação. Todas essas rotinas de movimentação foram feitas por um código proprietário que controla cada movimento da maquina mas como esse protótipo foi desenvolvido com uma plataforma não profissional ele possui limitações de velocidade de controle dos motores, problemas com aquecimento e o software precisa de correções e novas implementações para possibilitar ajustes de desenho sem precisar alterar o software como um todo e deixando a bobinadeira completamente stand alone. 

## 3. Proposta  
Utilizando de conceitos e aprendizados provenientes do curso de engenharia eletrônica, foi definido como projeto a elaboração de uma maquina para fabricação de bobinas para a industria de detectores de metais. A realização e o desenvolvimento da proposta será feita de acordo com a metodologia orientada à projetos denominada “Abordagem CDIO”, composta de 4 etapas: Concepção, Design, Implementação e Operação. A descrição de cada etapa será contextualizada no decorrer do trabalho.

## 4. Concepção

A bobinadeira e uma ferramenta utilizada no chão de fabrica e busca agilizar a produção da melhor maneira possível e com o menor auxilio possível de um colaborador, podendo assim reduzir o tempo de confecção dos sensores com a melhor precisão e qualidade de confecção.Seguindo esse pensamento, nesta etapa nós desenvolvedores devemos nos apropriar do contexto, definir os requisitos e meios para alcançar nossos objetivos, sendo estes:

* Realimentação de posição inicial;
* Sistema de controle de posição em caso de emergência;
* Controle de cargas, visando redução de detritos e controle do spindle;
* Sinalização auditiva/visual de processo concluído;
* Sistema de parada de emergência;
* IHM resistente ao chão de fabrica e que possa ser usada com luvas;
* Central para visualização de medidas dos sensores;
* Entrada e alteração das medidas dos sensores;
* Precisão de movimento com uma velocidade adequada;

Abaixo é apresentado o diagrama de blocos que resumem a concepção de funcionamento inicial que possibilita a partir dos requisitos acima selecionar como cada requisito sera atendido.
![Diagrama de blocos PI3](https://raw.githubusercontent.com/henrique-bento/Bobinadeira-CNC-PI-3/main/img_PI3/diagrama%20de%20blocos%20PI3.jpg)

