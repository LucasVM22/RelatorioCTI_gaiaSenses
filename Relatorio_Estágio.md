Este relatório procura narrar o meu trabalho voluntário como estagiário no projeto do CTI GaiaSenses, com descrições e informações sobre cada uma das implementações feitas por mim que foram integradas com sucesso no projeto. Comentarei sobre 3 implementações em particular. Conexão com um banco de dados online, restauração do sistema do painel de controle, e criação de uma API. 


  1. Banco de dados


É considerado uma boa prática em sistemas que utilizam dados dinâmicos registrar os resultados das requisições realizadas. A primeira tarefa atribuída a mim foi estabelecer a conexão entre o sistema GaiaSenses e um banco de dados online, com o objetivo de enviar as informações dos dados de satélite capturados em cada requisição, após a execução de uma animação. Esses dados seriam inseridos como uma nova linha em uma tabela no banco de dados.

<img width="512" height="293" alt="unnamed" src="https://github.com/user-attachments/assets/99817dec-d590-4309-bc49-d9c046ca360a" />

Cada um dos dados de satélite serviu como uma das colunas da table. São eles: 
name			Nome da animação tocada
temperature		Valor da temperatura
humidity		Valor da umidade
wind_speed		Valor da velocidade do vento
lightning_count	Número de ocorrências de raios
fireSpots_count	Número de focos de incêndios 
date_timeplayed	Data e horário que a animação foi tocada
pinnedlocation		Localização (lat e long) em que o usuário colocou o “pin”
userlocation		Localização do usuário quando a animação foi tocada
timeSpent		Tempo em que a animação ficou aberta até ser fechada

Para a implementação dessa funcionalidade, escolhi o Supabase (https://supabase.com/), uma plataforma gratuita que permite a criação de projetos e, posteriormente, a configuração de bancos de dados online. (link do banco do GaiaSenses: https://supabase.com/dashboard/project/iyuroutnhzvrwebihuyu).

<img width="512" height="252" alt="unnamed (1)" src="https://github.com/user-attachments/assets/d2e3ca16-78b4-4bd5-a093-53f527e65dca" />

A principal dificuldade encontrada durante a implementação da comunicação entre o projeto e o banco de dados foi compreender e diferenciar os conceitos de client-side e server-side em um projeto desenvolvido em TypeScript com React/Native. Um exemplo dessa complexidade foi a necessidade de utilizar hooks como useEffect e useRef para calcular o tempo gasto ("timeSpent") no lado do cliente, enquanto o acesso ao banco de dados ocorreu no lado do servidor.


  2. Painel de Debug


O Projeto GaiaSenses já tinha uma pasta chamada debug-panel, com a implementação velha de um painel de debug que não era mais usado, minha tarefa foi fazê-la voltar a funcionar. A ideia do painel de debug seria um botão que se posicionaria ao canto direito da tela enquanto a animação toca; os desenvolvedores do projeto poderiam então, alterar os valores de satélite nas lacunas do painel para observar as mudanças na animação em tempo real, facilitando os testes. Por exemplo, observar a cor de uma animação ir de laranja à azul quando o valor da temperatura é diminuído.

<img width="512" height="291" alt="unnamed (2)" src="https://github.com/user-attachments/assets/41d9f72b-c900-4153-911a-bc651f591848" />

Para a restauração do painel de debug, foi preciso repensar a lógica que controlava como o sistema gerencia as informações de satélite para o que ficou decidido: 
-capturar os dados de satélite iniciais
-permitir que o usuário altere os valores
-permitir que os valores iniciais sejam restaurados com um botão de “reset”

A nova lógica faz o sistema ler os parâmetros de cada animação para montar as lacunas onde os dados de satélite poderão ser acessados, sendo assim diferente para cada composição. Além disso, os dados de satélite são adquiridos da URL na barrinha de pesquisa como os valores iniciais, esses valores são salvos e restaurados quando o botão de reset é clicado. 


  3. API


À medida que um projeto cresce, ele pode começar a receber contribuições de terceiros e/ou pessoas que não estão diretamente envolvidas nele. Esta próxima implementação foi um simples arquivo que gera um link de API onde contribuidores do projeto GaiaSenses podem adquirir os dados de satélite em formato que nós adquirimos normalmente dentro do sistema (a partir de outras APIs), porém, em formato JSON, sem estarem com o projeto em mãos.
Basta alterar os valores de “lat” e “lon” para obter diferentes resultados desejados em outros lugares do mundo.

<img width="262" height="222" alt="unnamed (3)" src="https://github.com/user-attachments/assets/d4393bb1-1ad4-41d8-824e-dc7b07ccea17" />

http://localhost:3000/api/satellite?lat=-17&lon=50 - link gerado do código local.


  4. Experimento com reconhecimento facial


Um experimento foi proposto utilizando o GaiaSenses com a intenção de adquirir feedback de usuários a partir do uso de um programa que capta a reação das pessoas ao assistir o projeto em funcionamento.

<img width="491" height="476" alt="unnamed (4)" src="https://github.com/user-attachments/assets/070effb0-05f4-4295-90f3-ab2108838a7c" />

O código já disponível implementa um sistema de detecção de emoções faciais em tempo real usando uma webcam. Ele captura quadros de vídeo continuamente, aplica o modelo RFB-320 para localizar rostos no quadro, recorta as regiões faciais detectadas e utiliza um modelo ONNX (emotion-ferplus-8) para classificar emoções como felicidade, tristeza ou raiva. Cada emoção é mapeada para um sentimento positivo ou negativo, exibido visualmente no vídeo com caixas delimitadoras coloridas e labels. Os sentimentos são registrados em um arquivo CSV a cada 0,5 segundos, enquanto o vídeo processado é salvo em um arquivo AVI para análise posterior. O sistema roda em loop até o usuário pressionar 'q' para encerrar.

Após a coleta de 12 arquivos CSVs, foram selecionados os 5 arquivos onde houve atividade de captura de emoções para o desenvolvimento do outro programa criado para ajudar na visualização de tais resultados.

<img width="512" height="216" alt="unnamed (5)" src="https://github.com/user-attachments/assets/2e6f621b-5a1f-453b-982b-80669c665b0b" />

Neste programa criado depois do experimento, as ocorrências de emoções captadas como “happiness” (a emoção demonstrada além de “neutral”), foram interseccionados em um gráfico a partir dos 5 CSVs selecionados.

<img width="1200" height="500" alt="joinedGraph" src="https://github.com/user-attachments/assets/fde960ef-f49c-438c-8c53-1278670696f7" />

Assim, podemos concluir visualmente quais seções do vídeo foram as mais chamativas a partir deste gráfico plotado com python.
