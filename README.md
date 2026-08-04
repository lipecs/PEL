<h1 align="center">PELPlugin</h1>

<p align="center">
  Minigame completo de <strong>Polícia e Ladrão</strong> desenvolvido por Lipe.
</p>

<p align="center">
  <img alt="Java 17" src="https://img.shields.io/badge/Java-17-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white">
  <img alt="Paper" src="https://img.shields.io/badge/Paper-3C3C3C?style=for-the-badge&logo=paper&logoColor=white">
  <img alt="Maven" src="https://img.shields.io/badge/Maven-3-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white">
  <img alt="MySQL e SQLite" src="https://img.shields.io/badge/Banco-MySQL%20%7C%20SQLite-4479A1?style=for-the-badge&logo=mysql&logoColor=white">
</p>

## Sobre o projeto

O **PELPlugin** transforma o clássico Polícia e Ladrão em um minigame completo para servidores Minecraft. Policiais precisam capturar e impedir a fuga dos ladrões, enquanto os ladrões hackeiam objetivos, abrem rotas e tentam escapar antes do fim da partida.

> O projeto levou cerca de três anos para ser desenvolvido, passando por diversas etapas de planejamento, programação, testes e melhorias até chegar à sua versão atual.

O projeto não se limita à partida principal: ele possui múltiplos modos de jogo, kits, progressão, economia, cosméticos, missões, conquistas, salas personalizadas, modo história, criação visual de mapas e suporte a uma network com Velocity.

## Principais funcionalidades

- Partidas automáticas com times de **Policiais**, **Ladrões** e **Espectadores**.
- Objetivos de hack, prisão, captura, fuga e portas controladas pela partida.
- Criação de várias salas simultâneas para um mesmo mapa.
- Mundos temporários clonados por partida com **Advanced SlimeWorldManager**.
- Dez modos de jogo com regras próprias.
- Mais de vinte kits distribuídos entre policiais e ladrões.
- Salas personalizadas configuráveis e acessíveis por código.
- Modo história com objetivos sequenciais, áreas e batalha contra chefe.
- Sistema de níveis até o nível 1000, patentes e cinco prestígios.
- Economia com moedas, ouro, XP e recompensas configuráveis.
- Conquistas, missões diárias e semanais, títulos e temporadas.
- Loja de cosméticos, caixas misteriosas, chaves e efeitos visuais.
- Histórico de partidas, estatísticas detalhadas e rankings.
- Hologramas interativos de nível e vitórias: total, mensal e semanal.
- Sistema de reports, bans internos e ferramentas administrativas.
- NPCs de entrada para partidas normais e para o modo história.
- Integração com party, rejoin, preferências globais e comandos da network.
- Persistência em MySQL ou SQLite, com fallback local de emergência.
- API HTTP opcional para integração com loja web.
- Webhooks opcionais para eventos no Discord.

## Modos de jogo

| Modo | Funcionamento |
|---|---|
| **Tradicional** | Experiência clássica de Polícia e Ladrão. |
| **Fuga em Massa** | Um policial fortalecido enfrenta todos os ladrões. |
| **Rodízio** | Os times trocam de função a cada dois minutos. |
| **VIP** | Um time protege o VIP enquanto o outro tenta eliminá-lo. |
| **Contra-Relógio** | Os ladrões precisam hackear os computadores e fugir antes do tempo acabar. |
| **Roleta Russa** | Dois jogadores trocam de papel periodicamente. |
| **Espião** | Um ladrão infiltrado se passa por policial e pode ser descoberto por votação. |
| **Infecção** | Jogadores eliminados retornam como infectados; o último ladrão vivo vence. |
| **Dupla Dinâmica** | Duplas jogam com vida compartilhada. |
| **Caos Absoluto** | Uma roleta ativa eventos diferentes durante a partida. |

## Kits

### Ladrões

`Ladrão Padrão`, `Sortudo`, `Feiticeiro`, `Bomba de Fumaça`, `Metamorfose`, `Gancho`, `Hacker`, `Flash`, `Guerrilheiro`, `Rebobinar`, `Infestador`, `Estilingue` e `Falsificador`.

### Policiais

`Policial Padrão`, `Médico`, `Trapper`, `Taser`, `K-9`, `Rastreador`, `Escudo`, `Destruidor`, `Scanner`, `Rede` e `Pulso EMP`.

Cada kit possui habilidade e balanceamento próprios. O desbloqueio e a seleção ficam salvos no perfil do jogador.

## Progressão e perfil

O perfil armazena permanentemente:

- nível, XP, patente e prestígio;
- moedas, ouro e chaves de caixas;
- vitórias, derrotas, partidas e sequência de vitórias;
- abates, mortes, capturas, hacks e fugas;
- desempenho por modo e por time;
- progresso semanal e mensal;
- kits e cosméticos desbloqueados;
- missões, conquistas, títulos e histórico de partidas;
- preferências de interface, efeitos, mensagens e organização da hotbar.

O sistema de prestígio possui cinco etapas. Cada prestígio aumenta os multiplicadores de XP, moedas e ouro em partidas futuras.

## Cosméticos

O plugin possui uma camada de personalização integrada ao perfil:

- efeitos de abate, morte e vitória;
- trilhas e partículas;
- sprays em PNG ou GIF;
- mensagens de abate;
- títulos exibidos sobre o jogador;
- caixas misteriosas e chaves;
- loja e desbloqueios persistentes.

Cosméticos podem ser desativados individualmente pelas preferências do jogador e não alteram as regras competitivas da partida.

## Salas personalizadas

O criador de uma sala personalizada pode definir:

- mapa;
- duração da partida;
- horário fixo de dia ou noite;
- limite de jogadores;
- modo de jogo;
- uso ou bloqueio de kits;
- escolha manual ou sorteio balanceado dos times.

Cada sala recebe um código para entrada pelo comando global `/entrar <código>`. O dono organiza os times e decide quando iniciar. Por padrão, partidas personalizadas não concedem estatísticas nem recompensas.

## Modo história

O modo história utiliza sessões independentes e conduz o jogador por uma sequência de objetivos:

1. Ir até o pátio.
2. Encontrar o cartão de acesso.
3. Hackear a central de segurança.
4. Seguir pelos esgotos.
5. Chegar ao porto.
6. Derrotar o comandante Vargas.
7. Alcançar a extração.

O editor inclui regiões para esconderijo, central, esgotos, pátio, porto e chefe, além de partículas de visualização durante o setup.

## Mapas e instâncias

O PEL utiliza o **Advanced SlimeWorldManager (ASWM)** para exportar templates e criar uma cópia temporária do mapa para cada partida. Essa arquitetura oferece:

- isolamento completo entre partidas;
- várias salas do mesmo mapa em uma única instância Paper;
- descarte automático do mundo ao encerrar a sala;
- limpeza de mundos temporários após reinicializações inesperadas;
- proteção do mapa original contra alterações da partida.

O setup é feito dentro do jogo com itens próprios para posições, spawns, regiões, objetivos, preview e jump pads.

## Tecnologias

| Tecnologia | Uso no projeto |
|---|---|
| **Java 17** | Linguagem e runtime do plugin. |
| **Paper API** | Eventos, entidades, inventários e integração com o servidor. |
| **Maven** | Gerenciamento de dependências, build e empacotamento. |
| **ProtocolLib** | Compatibilidade com recursos baseados em pacotes. |
| **Advanced SlimeWorldManager** | Templates e mundos temporários por partida. |
| **HikariCP** | Pool de conexões com o banco de dados. |
| **MySQL Connector/J** | Persistência compartilhada em MySQL. |
| **SQLite JDBC** | Persistência local sem servidor de banco externo. |

## Requisitos

- Java 17.
- Compatível com Paper da versão 1.8.9 até a 1.21.1.
- ProtocolLib.
- Maven 3.8 ou superior para compilar.

## Configuração

As principais seções de `config.yml` são:

```yaml
network:       # lobby e sincronização de arenas
rooms:         # limite de salas por mapa
story:         # limite de sessões do modo história
scoreboard:    # rodapé e apresentação
aswm:          # templates, exportação e mundos temporários
database:      # mysql ou sqlite
gameplay:      # tempos, assistências e regras da partida
economy:       # recompensas de XP e moedas
auto-save:     # intervalo de salvamento de perfis
kits:          # balanceamento específico dos kits
discord:       # webhook opcional
events:        # eventos e multiplicadores de fim de semana
season:        # duração das temporadas
webstore:      # API HTTP da loja
```

Exemplo de banco MySQL:

```yaml
database:
  type: "mysql"
  host: "127.0.0.1"
  port: 3306
  database: "pel_plugin"
  username: "pel"
  password: "SENHA_FORTE"
```

Para uma instalação simples, altere `type` para `sqlite`. O banco será criado automaticamente na pasta do plugin.

## Comandos de jogador

| Comando | Função |
|---|---|
| `/pel salas` | Lista as salas disponíveis. |
| `/pel entrar <mapa>` | Entra em uma sala do mapa informado. |
| `/pel conquistas [jogador]` | Abre o menu de conquistas. |
| `/pel prestigio` | Exibe o progresso de prestígio. |
| `/pel tutorial` | Abre ou inicia o tutorial. |
| `/pel trails` | Abre a loja de trilhas. |
| `/pel missoes` | Exibe as missões diárias e semanais. |
| `/pel apostar <quantia>` | Realiza uma aposta na partida. |
| `/pel stats [jogador]` | Exibe estatísticas detalhadas. |
| `/pel titulo [nome]` | Lista ou seleciona um título. |
| `/pel historico` | Abre o histórico de partidas. |
| `/pel evento` | Exibe o evento ativo. |
| `/pel temporada` | Abre o ranking da temporada. |
| `/pel votar [jogador]` | Vota no suspeito durante o modo Espião. |
| `/l`, `/lobby`, `/hub` | Sai da partida ou retorna ao lobby. |
| `/g <mensagem>` | Envia uma mensagem ao chat global da arena. |

Com a integração do proxy ativa, `/entrar <código>` acessa salas por código e `/rejoin` reconecta o jogador à partida anterior.

## Comandos administrativos

| Comando | Função |
|---|---|
| `/pel criar <nome> <min> <max> <tempo>` | Inicia o setup de um mapa normal. |
| `/pel criar <nome> <min> <max> story` | Inicia o setup de um mapa de história. |
| `/pel deletar <nome>` | Remove um mapa normal ou de história. |
| `/pel setlobby` | Define o lobby do servidor PEL. |
| `/pel slimewand` | Entrega a ferramenta de seleção para exportação. |
| `/pel setpreview` | Define a posição de preview do mapa. |
| `/pel setjump` / `/pel deljump` | Cria ou remove um jump pad. |
| `/pel build` | Alterna o modo de construção administrativa. |
| `/pel iniciar` | Força o início da sala atual. |
| `/pel npc` | Cria o NPC de partidas normais. |
| `/pel npc story` | Cria o NPC do modo história. |
| `/pel removenpc` | Remove o NPC de partidas normais. |
| `/pel removenpc story` | Remove o NPC do modo história. |
| `/pel holograma nivel` | Cria o ranking de níveis. |
| `/pel holograma vitorias` | Cria o ranking de vitórias. |
| `/pel holograma remover <nivel|vitorias>` | Remove um ranking. |
| `/pel load <mundo>` | Carrega uma pasta de mundo e teleporta o administrador. |
| `/pel tp <mundo>` | Teleporta para um mundo carregado. |
| `/pel unload <mundo>` | Salva e descarrega um mundo vazio. |
| `/pel add <moeda|ouro|xp> <jogador> <quantia>` | Adiciona saldo ou XP. |
| `/pel set <moeda|ouro|xp|nivel> <jogador> <valor>` | Define um valor do perfil. |
| `/pel crate` / `/pel removecrate` | Cria ou remove uma caixa misteriosa. |
| `/pel givekey <jogador> <quantia>` | Entrega chaves de caixa. |
| `/pel spraygive <arquivo> [jogador]` | Entrega um spray PNG ou GIF. |
| `/pel hb` | Habilita ou desabilita as filas. |
| `/pel reload` | Recarrega as configurações principais. |

Comandos de teste, depuração e manutenção também existem, mas devem ser utilizados somente em ambiente administrativo.

## Permissões

| Permissão | Descrição | Padrão |
|---|---|---|
| `pel.admin` | Acesso à administração, setup e manutenção do minigame. | OP |

## Autor

Desenvolvido por **Lipe**

> O projeto está à venda. Estou aberto a propostas e negociações de pessoas realmente interessadas.

- GitHub: [github.com/lipecs](https://github.com/lipecs)

## Licença

Este projeto não possui uma licença open source definida. O código não pode ser redistribuído, revendido ou reutilizado sem autorização do autor.
