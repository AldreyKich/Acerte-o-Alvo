# Acerte-o-Alvo
Aplicativo Mobile desenvolvido no Android Studio

Projeto: Acerte o Alvo

Descrição: Aplicativo Android desenvolvido em Kotlin, cujo objetivo é um jogo simples de acertar o alvo.
O app registra a pontuação dos jogadores, salva os dados em SharedPreferences e exibe um Ranking com os 10 melhores resultados.

Estrutura do Projeto
1. Pacote principal (com.example.acerteoalvo)
 MainActivity.kt

Tela inicial do jogo.

Responsável por iniciar a partida e direcionar para o jogo em si.

Contém botões principais, incluindo acesso ao Ranking.

 GameActivity.kt

Tela onde o jogador interage com o jogo.

Controla:

Mecânica do disparo no alvo.

Cálculo da pontuação.

Exibição de mensagens de acerto/erro.

Ao final do jogo:

Pede o nome do jogador.

Salva o resultado no SharedPreferencesHelper.

 RankingActivity.kt

Exibe a lista de melhores pontuações (TOP 10).

Utiliza RecyclerView com RankingAdapter para mostrar:

Posição no ranking.

Nome do jogador.

Pontuação.

Lê os dados do SharedPreferencesHelper.

 SharedPreferencesHelper.kt

Classe auxiliar para salvar e carregar os dados do ranking.

Usa Gson para converter lista de objetos em JSON.

Funções principais:

saveScore(PlayerScore) → salva um novo resultado.

getRankingList() → retorna a lista de jogadores/pontuações.

 RankingAdapter.kt

Adaptador do RecyclerView para exibir o ranking.

Recebe lista de PlayerScore.

Liga cada item ao layout item_ranking.xml.

Mostra:

Posição.

Nome.

Pontuação.

2. Layouts XML
 activity_main.xml

Tela inicial do app.

Botões para iniciar o jogo e acessar o ranking.

 activity_game.xml

Layout da tela do jogo.

Contém:

Área para exibir o alvo.

Botões de disparo/ação.

Texto com pontuação atual.

 activity_ranking.xml

Layout da tela do ranking.

Inclui um RecyclerView para mostrar a lista de jogadores.

 item_ranking.xml

Layout de cada linha do ranking.

Mostra:

Posição (tvPosition).

Nome do jogador (tvName).

Pontuação (tvScore).

3. Recursos
 strings.xml

Centraliza textos usados no app (ex.: mensagens de vitória, botões, títulos).

 colors.xml

Define cores personalizadas do aplicativo.

 styles.xml

Contém estilos gerais do app (tema base, personalizações de UI).

4. Configuração
 AndroidManifest.xml

Declara todas as atividades (MainActivity, GameActivity, RankingActivity).

Define MainActivity como tela inicial (LAUNCHER).

 build.gradle

Configuração do projeto.

Inclui dependências como:

Gson (para salvar o ranking).

RecyclerView (para lista de ranking).

 Funcionamento do Ranking

O jogador joga uma partida.

Ao final, insere o nome.

O score é salvo em SharedPreferences via SharedPreferencesHelper.

Apenas os 10 melhores resultados são mantidos.

O RankingActivity carrega os dados e exibe no RecyclerView.

 Particularidades

Ranking limitado a 10 posições.

Dados persistem mesmo fechando o app (graças ao uso de SharedPreferences).

Fácil expansão para salvar em banco de dados no futuro.

 - 24/08/2025 - Criação do Projeto - Aldrey Kich
