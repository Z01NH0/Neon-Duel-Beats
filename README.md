# Neon Duel Beats — City Walk + Iron Fist + Vulcan Blood Stem Rework

Jogo de ritmo local para **2 jogadores**, desenvolvido com **p5.js**. Esta versão mantém a City Walk no fácil, a Iron Fist V3 no médio e reconstrói completamente o mapa da **Vulcan Blood** usando stems separados de bateria, baixo e guitarras.

Os stems foram usados somente durante a análise. O jogo continua usando o mesmo arquivo final `assets/vulcan-blood.ogg`; nenhum stem separado foi incluído no projeto.

## Como executar

1. Extraia o ZIP mantendo a pasta `assets` ao lado de `game.js`.
2. Abra a pasta no VS Code.
3. Execute `index.html` com a extensão **Live Server**.
4. Mantenha a internet ativa na primeira abertura, pois o p5.js é carregado por CDN.

As músicas são carregadas com `fetch` e Web Audio API. Abrir o `index.html` diretamente por `file://` pode bloquear o áudio.

## Controles padrão

- Jogador 1: `A`, `S`, `W`, `D`
- Jogador 2: setas `←`, `↓`, `↑`, `→`
- `ESC`: pausar ou continuar

Os oito controles podem ser alterados em **Configurações** e ficam salvos no navegador.

## Músicas

- **City Walk** — Fácil — aproximadamente 129 BPM.
- **Iron Fist** — Médio — aproximadamente 140 BPM.
- **Vulcan Blood** — Difícil — aproximadamente **195 BPM**.

## Vulcan Blood — reconstrução por stems

- Duração: aproximadamente 4 minutos e 29 segundos.
- BPM detectado pelo metrônomo: aproximadamente 194,985 BPM.
- 2.629 eventos rítmicos.
- 2.652 notas para cada jogador.
- 692 palm mutes confirmados, todos na pista mais à esquerda.
- 1.194 eventos guiados pela guitarra principal/lead.
- 1.435 eventos guiados por riffs e acordes.
- 23 acordes de impacto.
- 21 sustains para bends e notas prolongadas.
- J1 e J2 recebem exatamente o mesmo mapa.
- Nenhum palm mute é colocado nas regiões classificadas como solo.
- Nenhuma nota duplicada, intervalo inválido ou sustain conflitante.

A análise separa o comportamento do chart por seção:

- Nos riffs, a guitarra rítmica e os ataques secos confirmados pelo baixo/bateria produzem palm mutes na seta esquerda.
- Quando a guitarra lead entra, o chart suprime o riff de fundo e acompanha a linha principal nas outras três pistas.
- Bateria e baixo servem para confirmar pulsação e impactos, sem criar uma quantidade artificial de notas.
- Foi aplicada uma compensação de aproximadamente 23 ms entre os stems MP3 e o OGG usado pelo jogo.

## Cenários e multiplicadores

- Fácil: baía futurista com aurora, lua, cidade, reflexos, estrelas cadentes, drones e orbes.
- Médio: metrópole cyberpunk com tempestade elétrica, chuva neon, raios e veículos voadores.
- Difícil: vulcão, lava, fumaça, brasas, bolhas, gêiseres e erupções.
- Multiplicador individual: 1x, 2x aos 15 acertos, 3x aos 30 e 4x aos 45.
- Um erro reinicia somente o multiplicador do jogador responsável.
- Em 4x, apenas a pista daquele jogador recebe fogo e brilho reforçado.

## Estrutura

- `index.html` — interface e carregamento do p5.js.
- `styles.css` — menus e HUD.
- `game.js` — gameplay, mapas, sustains, controles e cenários.
- `assets/city-walk.ogg` — música fácil.
- `assets/iron-fist.ogg` — música média.
- `assets/vulcan-blood.ogg` — música difícil.
- `VALIDACAO_STEMS.txt` — relatório técnico do novo mapa.

## Compatibilidade p5.js

As curvas dos cenários possuem fallback para `splineVertex`, `curveVertex` e `vertex`, mantendo compatibilidade com versões diferentes do p5.js.
