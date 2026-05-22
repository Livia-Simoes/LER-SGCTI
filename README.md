## Documento de Especificação de Requisitos e Planejamento do Jogo: EcoCity
### Nome do Projeto:
#### EcoCity: Separação Inteligente do Lixo
<img width="1210" height="894" alt="Captura de tela 2026-05-22 161915" src="https://github.com/user-attachments/assets/e8f02542-8a22-42c8-b0af-49b96bdc57a1" />
<img width="1196" height="890" alt="Captura de tela 2026-05-22 161923" src="https://github.com/user-attachments/assets/746b15c3-6f35-4a13-8db4-c8fbc87b53d0" />
<img width="1209" height="901" alt="Captura de tela 2026-05-22 161945" src="https://github.com/user-attachments/assets/fa1c7b74-6db5-46e9-9328-9548a208937c" />
<img width="1214" height="913" alt="Captura de tela 2026-05-22 162004" src="https://github.com/user-attachments/assets/88161cb1-7719-4c10-915e-3afa923826ed" />

Tipo de Documento: Especificação de Requisitos e Planejamento de Projeto (V2)
Line Spacing: 1.15

### 1. Visão Geral do Jogo

O EcoCity: Separação Inteligente do Lixo é um jogo digital educativo focado em sustentabilidade e reciclagem. O objetivo do jogo é incentivar o descarte correto de resíduos urbanos, demonstrando de forma prática e interativa como as ações individuais impactam diretamente na redução da poluição das cidades.

### 1.1. Core Loop (Ciclo de Jogo)
O jogador controla um personagem em um cenário urbano, localiza resíduos espalhados, realiza a coleta e os transporta até a lixeira de cor correspondente. Cada ação gera um impacto imediato na pontuação de poluição do ambiente.

### 1.2. Análise de Requisitos (Engenharia de Software)
Para garantir a correta implementação do backlog visualizado no Kanban e no planejamento inicial, o escopo foi dividido em Requisitos Funcionais (RF) e Requisitos Não-Funcionais (RNF).

### 2. Requisitos Funcionais (RF)
ID

Nome do Requisito

Descrição Detalhada
 
#### RF-01

Movimentação do Personagem

O sistema deve permitir que o jogador movimente o personagem livremente pelo cenário bidimensional/tridimensional da cidade através dos comandos de input.

#### RF-02

Mecânica de Coleta (Pegar Lixo)

O personagem deve ser capaz de interagir e coletar um objeto de resíduo por vez ao se aproximar dele.

#### RF-03

Mecânica de Descarte (Lixeiras)

O sistema deve processar o descarte do resíduo quando o personagem interagir com uma das 5 lixeiras seletivas disponíveis.

#### RF-04

Validação de Acerto e Erro

O sistema deve validar se o tipo de lixo descartado corresponde à cor correta da lixeira. Em caso de acerto, o item some e exibe "Você acertou!". Em caso de erro, o item retorna à posição original e exibe "Você errou!".

#### RF-05

Sistema de Pontuação (Poluição)

O jogo deve iniciar com um contador de poluição em 150 pontos. O acerto subtrai 10 pontos; o erro soma 10 pontos. O objetivo é reduzir o indicador ao menor nível possível.


### 2.1. Requisitos Não-Funcionais (RNF)
RNF-01 (Usabilidade): A interface deve possuir feedback visual imediato e claro (mensagens textuais de acerto/erro de fácil leitura).

RNF-02 (Acessibilidade/Padrão): O mapeamento de cores das lixeiras deve seguir rigorosamente o padrão internacional de reciclagem (Azul, Vermelho, Verde, Amarelo, Marrom).

RNF-03 (Performance): O loop de verificação de colisão e atualização dos pontos de poluição deve ocorrer em tempo real, sem atrasos perceptíveis para o usuário.

### 3. Especificações Técnicas dos Elementos do Jogo

#### 3.1. Mapeamento de Resíduos e Lixeiras Coletoras
O cenário contará obrigatoriamente com 5 categorias de materiais, contendo exatamente 3 objetos distintos espalhados para cada tipo (totalizando 15 itens a serem recolhidos).

| tipo de residuo | cor da lixeira | comportamento em acerto | comportamento em erro |
| --------------- | -------------- | ----------------------  | --------------------- | 
| papel           | azul           | Mensagem "Você acertou!", o lixo desaparece, Poluição -10. | Mensagem "Você errou!", o lixo volta ao local de origem, Poluição +10. |
| plástico        | Vermelho       |  Mensagem "Você acertou!", o lixo desaparece, Poluição -10. | Mensagem "Você errou!", o lixo volta ao local de origem, Poluição +10. |
| Vidro           | Verde          |  Mensagem "Você acertou!", o lixo desaparece, Poluição -10. | Mensagem "Você errou!", o lixo volta ao local de origem, Poluição +10. |
| metal           | Amarelo        |  Mensagem "Você acertou!", o lixo desaparece, Poluição -10. | Mensagem "Você errou!", o lixo volta ao local de origem, Poluição +10. |
| Orgânico        | Marrom         |  Mensagem "Você acertou!", o lixo desaparece, Poluição -10. | Mensagem "Você errou!", o lixo volta ao local de origem, Poluição +10. |


### 4. Divisão de Trabalho da Equipe e Matriz de Responsabilidades
Para otimizar o desenvolvimento ágil mapeado no Kanban, a distribuição de tarefas entre os 4 desenvolvedores da equipe foi estruturada da seguinte forma:

Integrante 1 (Designer de Ambientes / Tech Artist): Responsável por estruturar e criar o cenário completo da cidade, definindo as zonas de spawn dos lixos e posições fixas das lixeiras.

Integrante 2 (Programador de Gameplay): Responsável pela criação do asset do personagem, programação da lógica de movimentação física e inputs do teclado/gamepad.

Integrante 3 (Programador de Sistemas de Jogo): Responsável pela criação das entidades de lixos e lixeiras, além de codificar as caixas de colisão (hitboxes) para a coleta e entrega dos objetos.

Integrante 4 (Programador de UI/UX e Lógica de Estado): Responsável por codificar o sistema dinâmico de pontuação de poluição, exibição das mensagens de acerto/erro na tela e controle das regras de fim de jogo.

### 5. Ciclo de Lançamentos e Backlog de Desenvolvimento (Roadmap)
#### Fase 1: Alta Prioridade (Mínimo Produto Viável - MVP)

Modelagem/Desenho e instanciação do Personagem Principal.

Criação dos prefabs e lógicas para os 5 tipos de lixo e suas respectivas 5 lixeiras seletivas.

Construção do script do Sistema de Acerto e Erro (validação de colisão e correspondência de cores).

##### Fase 2: Média Prioridade (Mecânicas de Engajamento)

Implementação da UI para exibição dinâmica dos pontos de poluição da cidade (iniciando em 150).

Programação dos modificadores aritméticos (+10 para falhas e -10 para acertos).

#### Fase 3: Baixa Prioridade (Polimento e Extensões)

Criação de animações de corrida e coleta para o personagem.

Estruturação de progressão por Fases (leveis urbanos com dificuldades crescentes).

Inclusão de um Timer (cronômetro) para bonificação por tempo.

Melhorias visuais gerais, efeitos de partículas ao pontuar e refinamento de shader do cenário.

### Reflexão 
#### Como o Kanban ajudou na organização do grupo?
ajudou a otimizar o processo 

#### Quais gargalos surgiram?
muitos problemas em relação a programação no scratch 

#### Houve excesso de tarefas em desenvolvimento?
não muito, porque a ideia do jogo era simples, mas mesmo assim houve dificuldades no processo de programar no scratch

#### O quadro ajudou na comunicação?
sim, ajudou a cada um não ter dúvida no que fazer

#### O Scratch facilitou o desenvolvimento?
para nós foi uma ferramenta difícil de usar porque não temos muito costume

#### O que poderia melhorar no fluxo da equipe?
fazer outra forma de divisão mais equilibrada, teve pessoas que fizeram mais coisas que outras
