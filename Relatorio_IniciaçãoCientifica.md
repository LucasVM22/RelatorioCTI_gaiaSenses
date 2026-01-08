Relatório de trabalho voluntário no CTI
Lucas V. Mielle

Este relatório procura narrar o meu trabalho como voluntário no projeto do CTI GaiaSenses, com descrições e informações sobre cada uma das animações produzidas por mim que foram integradas no projeto. As animações seguem a filosofia do projeto de conscientização do usuário sobre meio ambiente, demonstrando fenômenos da natureza a partir dessas animações dinâmicas, possibilitado pelo uso do aplicativo Satellite Fetcher em conjunto a elas: https://satellite-fetcher.up.railway.app/ 

Edição de vídeos.
Começando o meu trabalho voluntário no projeto GaiaSenses, fiz edições de vídeos que foram apresentados no evento UPA da Unicamp, essas edições foram feitas dos dias 4 a 7 de setembro de 2024
Vídeo UPA. 2024. https://drive.google.com/drive/folders/1ceEV_R89IxxlsN3dSzcMSnr-MITmizhF



Visual.

Animações Desenvolvidas

1. NightRain.
Agosto, 2024.
Comecei o trabalho na primeira animação para o projeto GaiaSenses, ela demonstra um fundo escuro e com objetos sendo criados em posições diferentes no topo da tela, esses objetos são programados para se moverem de cima para baixo, agindo como pingos de chuva. 
A dinamização desta animação foi feita usando a quantidade de objetos criados na tela e as suas cores. Quanto maior a umidade do local, mais objetos (pingos) são criados, e as suas cores variam de acordo com a temperatura no ambiente, variando do roxo (muito frio) até o vermelho (muito calor).
https://github.com/fmammoli/Gaiasenses-web/tree/main/components/compositions/night-rain


2.  WindLines, Versão 1
Agosto, 2024.
Comecei o trabalho para montar a segunda animação, escolhi trabalhar com o dado que indica a velocidade do vento. WindLines ilustra um fundo escuro que gera objetos em posições aleatórias pela tela, eles se movem pela tela em grupos variados enquanto deixam traços pela tela, a combinação desses componentes gera um efeito de vento na tela. 
De acordo com o quão alta for a velocidade dos ventos no local, mas rapidamente os objetos irão se mover pela tela.


3.  LightningBolts.
Setembro, 2024. Ao começar o trabalho na terceira animação,passei para a próxima opção dos dados de satélite disponíveis, a contagem de raios em uma área de 100 quilômetros centrada no usuário. 
A animação LightningBolts apresenta um fundo escuro sem atividade quando não há ocorrência de raios no local, caso contrário, a animação mostra uma quantidade de linhas de traços caóticos igual à quantidade de raios captada pelo satélite. Além disso, a velocidade em que os raios se movem mais rapidamente pela tela quanto mais a sua quantidade aumenta.
https://github.com/fmammoli/Gaiasenses-web/tree/main/components/compositions/lightning-bolts


4.  BurningTrees.
Outubro, 2024. Comecei meu trabalho na próxima animação, que utiliza uma lógica parecida com a anterior, exceto, ela procura por focos de incêndio pelas redondezas do usuário em um raio de 100 quilômetros. 
Essa animação gera objetos que se comportam de maneira similar à WindLines, eles são criados no plano escuro uns ao lado dos outros, e se deslocam de baixo para cima na tela.
Os objetos têm uma coloração verde para representar a flora, e caso não haja focos de incêndio aos arredores do usuário, a animação não muda. Caso contrário, ela começa a deletar os objetos verdes, deixando um rastro luminoso alaranjado atrás dos que vão sumindo. Conforme a contagem de focos de incêndio for maior, mais intenso é este efeito, deixando cada vez menos objetos verdes na tela.
https://github.com/fmammoli/Gaiasenses-web/tree/main/components/compositions/burning-trees


5.  WindLines, Versão 2
Essa animação foi alterada após uma revisão minha e com a opinião dos outros integrantes do projeto em reuniões passadas. Encontramos uma particularidade com a animação onde, em situações onde a velocidade do vento era muito grande, o efeito tracejado dos seus objetos formavam um efeito pontilhado na tela ao invés de linhas completas. Por isso trabalhei em uma solução para resolver o problema.
O resultado foi que, apesar do efeito pontilhado ter desaparecido, a animação agora exige mais do hardware onde ela está sendo carregada, resultando em quedas de quadros ao longo da sua ilustração. Resolvi salvar o código antigo no caso de algum dia resolvermos voltar a usar a primeira versão da animação WindLines.
https://github.com/fmammoli/Gaiasenses-web/tree/main/components/compositions/wind-lines


6.  RiverLines. 
Após uma reunião onde tivemos a oportunidade de revisar o propósito e significado por trás das animações, cheguei a conclusão de que a primeira animação que fiz, NightRain, não serve muito bem para representar o grau de umidade, já que a chuva não está ligada a esse tipo de dado.
Assim, iniciei mais um trabalho para desenvolver uma nova animação que pudesse representar a umidade de um local de maneira mais precisa. No dia 5 de Janeiro, comecei o trabalho em uma animação nova chamada RiverLines, ela mostra um fundo escuro com objetos sendo criados na base da tela, todos agrupados no meio, eles são assim projetados para cima, fazendo seu caminho até o topo da tela, dando a impressão de que o usuário está olhando para um rio ou córrego. Existe uma variação no caminho de cada um, para que o movimento não seja completamente igual entre todos eles. 
Essa animação faz uso dos mesmos dados de satélite da animação NightRain, umidade e temperatura, tendo a mesma lógica de que: quanto maior for a umidade, mais objetos serão criados na tela, dando a ideia de abundância, enquanto a cor deles varia de acordo com a temperatura, podendo ser do roxo (muito frio) até o vermelho (muito calor).
https://github.com/fmammoli/Gaiasenses-web/tree/main/components/compositions/river-lines



Sonoro

Aqui começa a seção onde iniciei a sonorização das animações que produzi. O processo consiste em adicionar arquivos de áudio em formatos .mp3 ou .wav para as vídeo composições, com o objetivo de elevar a experiência do usuário ao acessar uma animação. 

A filosofia por trás desse sistema é espelhar a natureza dinâmica das animações que, se comportam de maneiras diferentes de acordo com os dados de satélite que nunca são os mesmos, e refletir esse comportamento com os seus próprios sons também.


1. NightRain.
Novembro, 2024, iniciei o processo de sonorização da primeira animação que fiz, foram implementadas 3 trilhas de áudio para a NightRain, cada uma com um efeito de chuva diferente, partindo do mais fraco até o mais forte entre elas.
https://github.com/fmammoli/Gaiasenses-web/blob/main/public/audios/NRheavy.mp3
https://github.com/fmammoli/Gaiasenses-web/blob/main/public/audios/NRlight.mp3
https://github.com/fmammoli/Gaiasenses-web/blob/main/public/audios/NRmedium.mp3


2. WindLines.
Fevereiro, 2025, comecei a trabalhar na sonorização da animação WindLines. A filosofia do processo foi semelhante àquela da NightRain. Um trio de arquivos de áudio representando os sons que o vento produz em diferentes intensidades, de uma leve brisa a um vendaval.
https://github.com/fmammoli/Gaiasenses-web/blob/main/public/audios/wind-linesHeavy.wav
https://github.com/fmammoli/Gaiasenses-web/blob/main/public/audios/wind-linesLight.wav
https://github.com/fmammoli/Gaiasenses-web/blob/main/public/audios/wind-linesMedium.wav


3. LightningBolts
Março, 2025, fiz o mesmo para a terceira animação, LightningBolts, mas com 2 tipos de áudios diferentes. Um para baixa e outro para alta intensidade em relação à quantidade de raios detectados pelo sistema.
https://github.com/fmammoli/Gaiasenses-web/blob/main/public/audios/lightningBolts_High.mp3
https://github.com/fmammoli/Gaiasenses-web/blob/main/public/audios/lightningBolts_Low.mp3


4. BurningTrees
Ainda em Março, 2025, comecei o processo de sonorização da animação BurningTrees, como a LightningBolts, ela também foi adicionada com 2 arquivos de áudio, dessa vez seguindo a lógica de como a animação funciona. Caso não sejam encontrados focos de incêndio, a animação permanece com seus objetos sem serem “queimados”, portanto, usei um áudio que representa uma floresta pacífica, com barulhos de pássaros, vento e etc. Quando existem focos de incêndio perto do usuário, os objetos verdes são “queimados” e o áudio que se escuta é o de uma lareira.
https://github.com/fmammoli/Gaiasenses-web/blob/main/public/audios/burningTrees_audio.mp3
https://github.com/fmammoli/Gaiasenses-web/blob/main/public/audios/burningTrees_noFire.wav


5. RiverLines
No final de Março, 2025, o processo de sonorização da última animação que eu havia feito foi iniciado. Para a animação RiverLines, decidi seguir o mesmo caminho das 2 primeiras animações, com 2 arquivos de áudio representando 2 níveis de intensidade da velocidade da água. Um dos áudios parece com um córrego calmo, e o outro um rio mais agitado.
https://github.com/fmammoli/Gaiasenses-web/blob/main/public/audios/riverLines_strong.wav
https://github.com/fmammoli/Gaiasenses-web/blob/main/public/audios/riverLines_weak.wav


