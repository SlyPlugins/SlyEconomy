# 💰 SlyEconomy

<p align="center">
  <img src="https://img.shields.io/badge/Minecraft-1.21.5-green?style=for-the-badge&logo=minecraft" alt="Minecraft"/>
  <img src="https://img.shields.io/badge/Java-21-orange?style=for-the-badge&logo=openjdk" alt="Java"/>
  <img src="https://img.shields.io/badge/Version-1.0.1-blue?style=for-the-badge" alt="Version"/>
  <img src="https://img.shields.io/badge/License-MIT-purple?style=for-the-badge" alt="License"/>
</p>

<p align="center">
  <b>O sistema de economia mais completo para Servidores Minecraft</b><br>
  Desenvolvido por <a href="https://slyplugins.com.br">SlyPlugins</a> | Modificado por <b>Slyvok</b>
</p>

---

## 📋 Índice

- [Sobre](#-sobre)
- [Funcionalidades](#-funcionalidades)
- [Requisitos](#-requisitos)
- [Instalação](#-instalação)
- [Comandos](#-comandos)
- [Permissões](#-permissões)
- [Placeholders](#-placeholders)
- [Configuração](#%EF%B8%8F-configuração)
- [API para Desenvolvedores](#-api-para-desenvolvedores)
- [Integrações](#-integrações)
- [Build](#-build)
- [Suporte](#-suporte)

---

## 📖 Sobre

**SlyEconomy** é um plugin de economia completo e moderno para servidores Minecraft, oferecendo uma experiência rica tanto para jogadores quanto para administradores. Com suporte a MySQL/SQLite, ranking visual por NPCs, sistema de bolsa de valores, cheques e muito mais.

### ✨ Destaques

- 🏦 **Menu de Banco** - Interface intuitiva para gerenciar dinheiro (FastInv)
- 📊 **Ranking Visual** - NPCs, ArmorStands e Hologramas
- 📈 **Bolsa de Valores** - Sistema dinâmico de valorização/desvalorização
- 💳 **Sistema de Cheques** - Transfira dinheiro de forma física
- 🔗 **Integração Discord** - Gerencie economia pelo Discord
- 🔌 **API Robusta** - Fácil integração com outros plugins
- ⚡ **Performance** - Cache assíncrono e otimizações modernas

---

## 🚀 Funcionalidades

### 🏦 Sistema Bancário
- Menu central com histórico de transações
- Envio de dinheiro entre jogadores
- Toggle de recebimento de moedas
- Visualização de saldo próprio e de outros

### 💳 Sistema de Cheques
- Criar cheques com qualquer valor
- Enviar cheques diretamente para outros jogadores
- Resgatar cheques individualmente ou em lote (agachado)
- Consultar valor de cheques sem resgatar
- Efeitos visuais e sonoros

### 📈 Bolsa de Valores
- Valorização/desvalorização automática
- Afeta transações de plugins externos
- Configuração de valores mínimo/máximo
- Mensagens de atualização personalizáveis

### 📊 Sistema de Ranking
| Tipo | Descrição |
|------|-----------|
| **Chat** | Ranking textual no chat |
| **Menu** | Interface gráfica com inventário |
| **NPC** | NPCs com skins dos top players |
| **ArmorStand** | Bonecos com hologramas |
| **Holograma** | Linhas flutuantes de texto |

### 🔗 Integração Discord (DiscordSRV)
- Consultar saldo pelo Discord
- Iniciar e confirmar transações
- Comandos customizáveis
- Vinculação de contas

---

## 📋 Requisitos

| Requisito | Versão | Obrigatório |
|-----------|--------|-------------|
| Spigot/Paper | 1.21.5+ | ✅ Sim |
| Java | 21+ | ✅ Sim |
| Vault | 1.7+ | ✅ Sim |
| PlaceholderAPI | 2.11+ | ❌ Opcional |
| HolographicDisplays | 2.4+ | ❌ Opcional |
| DecentHolograms | 2.8+ | ❌ Opcional |
| ProtocolLib | Última | ❌ Opcional* |
| PacketEvents | Última | ❌ Opcional* |
| DiscordSRV | 1.24+ | ❌ Opcional |

> *Necessário para ranking por NPC

---

## 📥 Instalação

1. **Baixe** o arquivo `SlyEconomy-1.0.1.jar` dos [Releases](https://github.com/SlyPlugins/SlyEconomy/releases)
2. **Coloque** o arquivo na pasta `plugins/` do servidor
3. **Instale** o [Vault](https://www.spigotmc.org/resources/vault.34315/) (obrigatório)
4. **Instale** dependências opcionais conforme necessário
5. **Reinicie** o servidor
6. **Configure** os arquivos em `plugins/SlyEconomy/`

---

## 💻 Comandos

### Comandos Gerais

| Comando | Descrição | Permissão |
|---------|-----------|-----------|
| `/money` `/coins` `/banco` | Abrir menu do banco | Nenhuma |
| `/money ver [jogador]` | Ver saldo de um jogador | Nenhuma |
| `/money enviar <jogador> <valor>` | Enviar dinheiro | `slyeconomy.command.pay` |
| `/money top` | Ver ranking de riqueza | Nenhuma |
| `/money toggle` | Ativar/desativar recebimento | `slyeconomy.togglecoins` |
| `/money vincular` | Vincular conta ao Discord | Nenhuma |
| `/money desvincular` | Desvincular conta do Discord | Nenhuma |
| `/money ajuda` | Ver comandos disponíveis | Nenhuma |

### Comandos de Cheque

| Comando | Descrição | Permissão |
|---------|-----------|-----------|
| `/cheque` | Ver ajuda do sistema de cheques | `slyeconomy.command.check` |
| `/cheque criar <valor> [jogador]` | Criar um cheque | `slyeconomy.command.check` |
| `/cheque info` | Ver valor do cheque na mão | `slyeconomy.command.check` |
| `/cheque total` | Ver total de cheques no inventário | `slyeconomy.command.check` |

### Comandos de Bolsa

| Comando | Descrição | Permissão |
|---------|-----------|-----------|
| `/bolsa` | Ver informações da bolsa | Nenhuma |
| `/bolsa give <jogador> <valor>` | Dar dinheiro baseado na bolsa | `slyeconomy.command.purse` |
| `/setbolsa <valor>` | Definir valor da bolsa | `slyeconomy.setpurse` |

### Comandos Administrativos

| Comando | Descrição | Permissão |
|---------|-----------|-----------|
| `/money set <jogador> <valor>` | Definir saldo | `slyeconomy.command.set` |
| `/money add <jogador> <valor>` | Adicionar dinheiro | `slyeconomy.command.add` |
| `/money remove <jogador> <valor>` | Remover dinheiro | `slyeconomy.command.remove` |
| `/money reset <jogador>` | Zerar conta | `slyeconomy.command.reset` |
| `/money npc add <posição>` | Adicionar NPC do ranking | `slyeconomy.command.npc.add` |
| `/money npc remove <posição>` | Remover NPC do ranking | `slyeconomy.command.npc.remove` |

### Comandos SlyEconomy

| Comando | Descrição | Permissão |
|---------|-----------|-----------|
| `/se` `/slyeconomy` | Comandos administrativos | `slyeconomy.admin` |
| `/se reload` | Recarregar configurações | `slyeconomy.admin` |
| `/se converter <plugin>` | Converter de outro plugin | `slyeconomy.admin` |
| `/se backup [nome]` | Criar backup | `slyeconomy.admin` |
| `/se read <arquivo>` | Restaurar backup | `slyeconomy.admin` |
| `/se forceupdate` | Forçar atualização do ranking | `slyeconomy.admin` |

---

## 🔐 Permissões

| Permissão | Descrição |
|-----------|-----------|
| `slyeconomy.admin` | Acesso a comandos administrativos |
| `slyeconomy.command.pay` | Enviar dinheiro a outros |
| `slyeconomy.command.check` | Usar sistema de cheques |
| `slyeconomy.command.set` | Definir saldo de jogadores |
| `slyeconomy.command.add` | Adicionar dinheiro |
| `slyeconomy.command.remove` | Remover dinheiro |
| `slyeconomy.command.reset` | Resetar contas |
| `slyeconomy.command.npc.add` | Adicionar NPCs do ranking |
| `slyeconomy.command.npc.remove` | Remover NPCs do ranking |
| `slyeconomy.togglecoins` | Ativar/desativar recebimento |
| `slyeconomy.setpurse` | Alterar valor da bolsa |
| `slyeconomy.bypass` | Enviar para quem desativou recebimento |
| `slyeconomy.command.help.staff` | Ver comandos de staff na ajuda |

---

## 🏷️ Placeholders

### PlaceholderAPI

| Placeholder | Descrição |
|-------------|-----------|
| `%slyeconomy_amount%` | Saldo do jogador |
| `%slyeconomy_purse%` | Valor da bolsa (ex: 28%) |
| `%slyeconomy_purse_only_value%` | Valor da bolsa apenas número |
| `%slyeconomy_purse_with_icon%` | Valor da bolsa com ícone |
| `%slyeconomy_tycoon%` | Tag de magnata/rico |
| `%slyeconomy_tycoon_name%` | Nome do jogador magnata |
| `%slyeconomy_top_1_name%` | Nome do top 1 (1-10) |
| `%slyeconomy_top_1_amount%` | Saldo do top 1 (1-10) |

> **Nota:**  
> - Para FeatherBoard: `{placeholderapi_slyeconomy_...}`  
> - Todos os placeholders e permissões usam o prefixo `slyeconomy`.  

### Chat (LegendChat, nChat, UltimateChat)

| Tag | Descrição |
|-----|-----------|
| `{tycoon}` | Tag de magnata ou rico |

---

## ⚙️ Configuração

### Arquivos de Configuração

| Arquivo | Descrição |
|---------|-----------|
| `configuration.yml` | Configurações gerais, banco de dados, bolsa, cheques |
| `messages.yml` | Todas as mensagens do plugin |
| `inventories.yml` | Configuração dos menus/GUIs |
| `ranking.yml` | Configuração do sistema de ranking |
| `npcs.yml` | Localizações dos NPCs do ranking |
| `discord.yml` | Configuração da integração Discord |
| `conversors.yml` | Configuração de conversores de economia |

### Banco de Dados

```yaml
database:
  type: 'sqlite'  # Opções: 'sqlite' ou 'mysql'
  mysql:
    address: 'localhost:3306'
    username: 'root'
    password: ''
    database: 'slyeconomy'
  sqlite:
    file: 'database/database.db'
```

### Sistema de Cheques

```yaml
check:
  enable: true
  min-value: 1000000
  item:
    display-name: '&a&l💳 Cheque'
    material: PAPER
    lore:
      - '&7┃ Valor: &f$amount'
      - '&eClique &fpara resgatar'
      - '&eAgache + Clique &fpara resgatar todos'
```

### Bolsa de Valores

```yaml
purse:
  enable: true
  media: 100      # Valor médio (acima = alta, abaixo = queda)
  minValue: 75    # Valor mínimo
  maxValue: 125   # Valor máximo
  nextUpdate: 600 # Intervalo de atualização (segundos)
```

---

## 🔌 API para Desenvolvedores

### Maven/Gradle

Para usar a API do SlyEconomy em seu plugin, adicione como dependência:

```gradle
dependencies {
    compileOnly 'com.slyplugins:SlyEconomy:1.0.1'
}
```

### Exemplos de Uso

```java
// Obter instância da API
SlyEconomyAPI api = SlyEconomyAPI.getInstance();

// Buscar conta de um jogador
Account account = api.findAccountByPlayer(player);

// Verificar saldo
double balance = account.getBalance();

// Criar transação
account.createTransaction(
    Transaction.builder()
        .player(player)
        .amount(1000)
        .transactionType(TransactionType.DEPOSIT)
        .build()
);

// Obter top player
SimpleAccount topPlayer = api.getTopPlayer(false);

// Abrir menu do banco para um jogador
InventoryRegistry registry = InventoryRegistry.getInstance();
BankView bankView = registry.getBankView();
bankView.openInventory(player);
```

### Eventos Disponíveis

| Evento | Descrição |
|--------|-----------|
| `MoneyChangeEvent` | Quando saldo de um jogador muda |
| `MoneyGiveEvent` | Quando dinheiro é adicionado |
| `MoneyWithdrawEvent` | Quando dinheiro é removido |
| `MoneySetEvent` | Quando saldo é definido |
| `TransactionRequestEvent` | Quando transação é solicitada |
| `AsyncRankingUpdateEvent` | Quando ranking é atualizado |
| `AsyncPurseUpdateEvent` | Quando bolsa é atualizada |
| `AsyncMoneyTopPlayerChangedEvent` | Quando top 1 muda |

### Utilitário de Cheques

```java
// Verificar se item é um cheque
boolean isCheck = CheckUtil.isCheck(itemStack);

// Obter valor do cheque
double value = CheckUtil.getCheckValue(itemStack);

// Criar cheque
ItemStack check = CheckUtil.createCheck(50000);
```

---

## 🔗 Integrações

### Plugins Suportados

| Plugin | Tipo | Funcionalidade |
|--------|------|----------------|
| **Vault** | Economia | Compatibilidade universal |
| **PlaceholderAPI** | Placeholders | Exibir informações em qualquer lugar |
| **DiscordSRV** | Discord | Comandos e notificações |
| **HolographicDisplays** | Hologramas | Ranking visual |
| **DecentHolograms** | Hologramas | Ranking visual |
| **ProtocolLib** | NPCs | NPCs do ranking |
| **PacketEvents** | NPCs | NPCs do ranking |
| **LegendChat** | Chat | Tag de magnata |
| **nChat** | Chat | Tag de magnata |
| **UltimateChat** | Chat | Tag de magnata |
| **CMI** | Utilitários | Compatibilidade |
| **SkinsRestorer** | Skins | Skins nos NPCs |

### Conversores de Economia

O SlyEconomy pode converter dados de outros plugins de economia:

- AtlasEconomy
- EssentialsX
- iConomy
- JHEconomy
- SOEconomy
- SolaryEconomy
- StormEconomy
- TuskEconomy
- yStore

Use: `/se converter <plugin>`

---

## 🔨 Build

### Requisitos

- Java 21+
- Gradle 8.7+ (incluído via wrapper)

### Dependências Principais

| Dependência | Versão | Descrição |
|------------|--------|------------|
| FastInv | 3.0.3 | Sistema de inventários GUI |
| SQL Provider | 9561f20fd2 | Gerenciamento de banco de dados |
| Configuration Injector | 1.0.2 | Injeção de configurações |
| Command Framework | 1.2.0 | Framework de comandos |
| Item NBT API | 2.11.3 | Manipulação de NBT |
| Caffeine | 3.1.8 | Sistema de cache |
| NPC Lib | 3.0.0-beta.16 | Sistema de NPCs |

### Compilar

```bash
# Windows
.\gradlew.bat clean build --no-daemon

# Linux/Mac
./gradlew clean build --no-daemon
```

O arquivo `.jar` será gerado em `build/libs/SlyEconomy-1.0.1.jar`

### Notas de Desenvolvimento

- **FastInv**: O plugin utiliza FastInv 3.0.3 para gerenciamento de inventários GUI, substituindo a antiga `inventory-api`
- **ShadowJar**: Todas as dependências são incluídas no JAR final
- **Lombok**: Utilizado para reduzir boilerplate code
- **Cache**: Sistema de cache assíncrono com Caffeine para melhor performance

---

## ❓ Problemas Comuns

### NPCs não aparecem
- Verifique se **ProtocolLib** ou **PacketEvents** está instalado
- Confirme as posições em `npcs.yml`
- Garanta que os chunks estão carregados

### Sons inválidos
- Use sons compatíveis com 1.21.5
- Exemplo: `BLOCK_NOTE_BLOCK_PLING`

### Cabeças de jogador não carregam
- Em versões novas usa-se `Material.PLAYER_HEAD`
- Verifique conexão com servidores da Mojang

### Erro de banco de dados
- Verifique credenciais MySQL
- Para SQLite, verifique permissões de escrita
- Confira o caminho do arquivo

### Menus não abrem
- Verifique se o FastInv está sendo carregado corretamente
- Confira os logs do servidor para erros de compilação
- Certifique-se de que todas as dependências estão presentes

---

## 📊 Estatísticas

<p align="center">
  <a href="https://bstats.org/plugin/bukkit/SlyEconomy">
    <img src="https://bstats.org/signatures/bukkit/SlyEconomy.svg" alt="bStats"/>
  </a>
</p>

> Nota: As estatísticas ainda aparecem como "NextEconomy" no bStats devido ao ID do plugin original.

---

## 💬 Suporte

  - **Discord:** [slyplugins.com.br/discord](https://slyplugins.com.br/discord)
  - **Issues:** [GitHub Issues](https://github.com/SlyPlugins/SlyEconomy/issues)
- **Wiki:** [GitHub Wiki](https://github.com/SlyPlugins/SlyEconomy/wiki)

---

## 📝 Changelog

### Versão 1.0.1

- ✨ **Migração para FastInv**: Substituição completa do `inventory-api` pelo FastInv 3.0.3
- 🐛 **Correções**: Correção de múltiplos erros de compilação e duplicação de código
- ⚡ **Performance**: Otimizações no sistema de cache e carregamento de dados
- 🔧 **Dependências**: Atualização de dependências para versões mais recentes
- 📦 **Build**: Melhorias no processo de build e empacotamento

---

## 📜 Licença

Este projeto está licenciado sob a [Licença MIT](LICENSE).

---

<p align="center">
  Criado por <b>SlyPlugins</b> - <b>SlyEconomy</b><br>
  <small>Versão 1.0.1 </small>
</p>
