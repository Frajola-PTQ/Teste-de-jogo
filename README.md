⚽ Football Master Brasil (FM BR)
Simulador de gerenciamento de clube de futebol focado no Brasileirão.
Desenvolvido em Python (Android/Pydroid3) com versão web em React.

🎮 O que é
FM BR é um simulador de gerenciamento de futebol em modo texto (Python/terminal) com versão web paralela em React. O jogador controla um ou mais clubes do Brasileirão, gerenciando elenco, participando do mercado de transferências e acompanhando a tabela de classificação ao longo de uma temporada completa de 38 rodadas.
✅ Funcionalidades implementadas
Módulo
Descrição
Temporada
38 rodadas (turno + returno), calendário round-robin, simulação baseada em OVR médio com fator aleatório
Tabela
Classificação completa com pontos, saldo de gols, vitórias/empates/derrotas
Mercado
Fluxo por posição (GOL→ZAG→MEI→ATA): venda, exibição do mercado, compra, IA automática
Leilão
Lances alternativos entre clubes quando dois querem o mesmo jogador
Geração de jogadores
Script Python gera 1.000 free agents com atributos, estrelas (1★–3★), faixas etárias e valor de mercado por fórmula
Banco de dados
CSV + JSONs indexados por posição, faixa e bucket de mercado
Notícias
30 notícias procedurais de mercado (rise, resurgence, rumor, scout report)
Versão Web
React autossuficiente (.jsx único): rodadas, tabela, elencos editáveis, mercado com log
🗂️ Estrutura do projeto
Simulador/
├── main_temporada.py           # Ponto de entrada
├── mercado_engine.py           # Motor do mercado
├── leilao_engine.py            # Menus + leilão interativo
├── fm_core/
│   ├── evolucao.py             # Evolução de jogadores
│   ├── valor.py                # Cálculo de valores
│   └── adapter.py              # Camada de compatibilidade
├── data/clubes/                # JSONs dos 20 times
├── database/
│   ├── freeagents_full.csv     # 1.000 free agents
│   ├── freeagents_market_buckets.json
│   ├── freeagents_by_position.json
│   └── midseason_news.json
└── simulador_br.jsx            # Versão web (React)
⚙️ Como rodar
Android (Pydroid3)
# Na pasta Simulador/:
python main_temporada.py
Versão Web
Abra simulador_br.jsx em qualquer sandbox React (CodeSandbox, StackBlitz, etc.) ou importe num projeto com React + Tailwind.
🧮 Fórmula de valor de mercado
base         = ovr * 0.6 + estrelas * 15
mult_idade   = 1.4 if idade <= 21 else (1.0 if idade <= 30 else 0.7)
mult_estrela = {1: 0.7, 2: 1.0, 3: 1.5}[estrelas]
preco        = max(20, round(base * mult_idade * mult_estrela))
🏟️ Times disponíveis (20)
Flamengo · Palmeiras · Atlético-MG · Botafogo · São Paulo · Internacional · Grêmio · Corinthians · Fluminense · Athletico-PR · Bahia · Cruzeiro · Fortaleza · Vasco · Santos · RB Bragantino · Chapecoense · Juventude · Sport · Cuiabá
🚧 Próximas features
[ ] Exibição de notícias de mercado no jogo
[ ] Evolução de jogadores ao virar temporada
[ ] Sistema de rebaixamento e acesso
[ ] Libertadores, Sul-Americana e Copa do Brasil
[ ] Save/Load de temporada
👤 Autor
Patrick Braga
Estudante de Jornalismo apaixonado por futebol, dados e desenvolvimento de jogos.
Projeto construído inteiramente com Python, React e IA como copiloto de desenvolvimento.
📄 Licença
MIT — livre para usar, modificar e distribuir.