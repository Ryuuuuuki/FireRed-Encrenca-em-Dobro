# Pokémon FireRed Duo — Encrenca em Dobro (beta)

**A two-player online Nuzlocke for Pokémon FireRed.** Each player runs their own game on their own PC, and every trainer battle is a co-op double battle against two clones of the trainer.

*(Português mais abaixo.)*

![Title screen](imagens/01_titulo.png)

## ⬇️ Download
- **[FireRedDuo_Beta_v0.1.zip](https://github.com/Ryuuuuuki/FireRed-Encrenca-em-Dobro/releases/download/v0.1-beta/FireRedDuo_Beta_v0.1.zip)** — the full kit (start here): patch + portable mGBA + connection script + server + guides.
- [FireRedDuo_Beta_v0.1.bps](https://github.com/Ryuuuuuki/FireRed-Encrenca-em-Dobro/releases/download/v0.1-beta/FireRedDuo_Beta_v0.1.bps) — just the patch.
- All versions: [Releases](https://github.com/Ryuuuuuki/FireRed-Encrenca-em-Dobro/releases).


> ⚠️ **Beta.** It's playable from start to finish in what we tested, but expect bugs. If the game crashes, please report what you were doing (map, battle, capture, bike/surf, emote) and a screenshot.

## Features
- **Co-op trainer battles:** when one player meets a trainer, the partner gets an invite and joins. You fight side by side against two clones of the trainer, each with half of its team. The rival brings each player's version of their team.
- **Run modes:** Classic, Soul Link, Hardcore and Casual, plus run rules: first encounter per player or shared, dupes clause, shiny clause, forced nicknames, level cap, battle item limit, EXP share.
- **Randomizer (optional):** wild Pokémon (random or by type), trainers, abilities, starters and gifts.
- **Difficulty:** Vanilla, Hard or Elite trainer teams, with Pokémon from every generation.
- **Play together:** see your partner walking on your map (as a "ghost"), send emotes, trade Pokémon, send items, and see each other on the Town Map.
- **Quality of life:** move relearner in the summary screen (START on the moves page), instant text speed, per-route encounter map, and a GRAVES box for fallen Pokémon.
- **Crash recovery:** the host can roll the run back to both players' last save.
- **Jessie & James** of Team Rocket as the two protagonists.

![Co-op battle](imagens/02_batalha_coop.png)

## What you need
- **Your own ROM** of *Pokémon FireRed (USA, Europe) Rev 1* (`.gba`). The patch only works on that version (not 1.0). **No ROM is provided here.**
- Windows (Linux works too, see the guide in the kit).
- Both players on the same network: [Radmin VPN](https://www.radmin-vpn.com/) is the simplest (Windows); [Tailscale](https://tailscale.com/) works on Windows and Linux.
- The player who hosts needs [Node.js](https://nodejs.org) (LTS) installed to run the server.

## How to play (step by step)

### 1. Download and unzip the kit
Download **[FireRedDuo_Beta_v0.1.zip](https://github.com/Ryuuuuuki/FireRed-Encrenca-em-Dobro/releases/download/v0.1-beta/FireRedDuo_Beta_v0.1.zip)** and unzip it into any folder (for example `Desktop\FireRedDuo`). Both players do this.

### 2. Check your ROM
You need your own copy of **Pokémon - FireRed Version (USA, Europe) (Rev 1)**, a 16 MB `.gba` file. The patch only works on this exact version. When you load it in Rom Patcher JS (next step), it shows the ROM's checksums; they must match:

| | |
|---|---|
| CRC32 | `84EE4776` |
| SHA-1 | `DD5945DB9B930750CB39D00C84DA8571FEEBF417` |

If it shows anything else (for example, the 1.0 version, CRC32 `DD88761C`), the game won't work.

### 3. Apply the patch
1. Open **[Rom Patcher JS](https://www.marcrobledo.com/RomPatcher.js/)** (it runs in your browser, nothing to install).
2. **ROM file:** pick your FireRed `.gba`. Check the CRC32 it shows (step 2).
3. **Patch file:** pick `FireRedDuo.bps` from the kit folder.
4. Click **Apply patch** and save the file.
5. Inside the kit folder, create a folder named `jogo` and put the file there, renamed to **`FireRedDuo.gba`**. It should end up as `jogo\FireRedDuo.gba`.

### 4. Get on the same network
1. Both install **[Radmin VPN](https://www.radmin-vpn.com/)** (Windows). With a Linux player, use **[Tailscale](https://tailscale.com/)** instead (guide in `README_EN.txt`, step 9).
2. The host creates a network (*Network > Create network*); the other joins it (*Network > Join an existing network*).
3. Radmin shows each player's IP (it starts with `26.`).
4. Both open `servidor.txt` (in the kit folder) with Notepad, replace `127.0.0.1` with **the host's** Radmin IP, and save.

### 5. Start the server (host only)
1. Install **[Node.js](https://nodejs.org)** (LTS version).
2. Double-click `Hospedar_servidor.bat` and keep that window open while you play. If Windows asks about network access, click **Allow**.

### 6. Open the game (both players)
1. Double-click `Jogar.bat`. (If Windows says "Windows protected your PC", click **More info > Run anyway**.)
2. In mGBA: **Tools > Scripting... > File > Load script...** and pick `client\duonet.lua`. Leave the Scripting window open. You do this every time you open the game; next times use *File > Load recent script*.

### 7. Start the run
1. **New Game.** After Professor Oak's intro, the **DUO** menu opens (also in *Start > DUO*).
2. One player picks **Create room**, sets the rules and gets a 6-letter code.
3. The other picks **Enter code** and types it.
4. From now on, every trainer battle is a co-op battle: whoever meets the trainer invites, the partner accepts.

More details (fast forward, crash recovery, Linux) are in `README_EN.txt` inside the kit. The game itself is in English.

## Known issues
- **Rare crashes reported** ("Jumped to invalid address", "OUT OF SPRITE SLOTS"). We could not reproduce them yet. The game saves after every battle and capture; if it crashes, both players close the game and the host runs `Voltar_ultimo_ponto.bat` with the room code.
- **The VS Seeker doesn't work** in this base.
- At the end of a co-op battle, the Win/Loss screen cuts long trainer names to 7 letters.

## Credits
Built on [pokeemerald-expansion](https://github.com/rh-hideout/pokeemerald-expansion) (RHH) and the FireRed decomp. Emulator: [mGBA](https://mgba.io) (bundled portable, under its own license). Pokémon is © Nintendo / Creatures / GAME FREAK. This is a non-commercial fan project.

---

# Português

## ⬇️ Download
- **[FireRedDuo_Beta_v0.1.zip](https://github.com/Ryuuuuuki/FireRed-Encrenca-em-Dobro/releases/download/v0.1-beta/FireRedDuo_Beta_v0.1.zip)** — o kit completo (comece por aqui): patch + mGBA portátil + script de conexão + servidor + guias.
- [FireRedDuo_Beta_v0.1.bps](https://github.com/Ryuuuuuki/FireRed-Encrenca-em-Dobro/releases/download/v0.1-beta/FireRedDuo_Beta_v0.1.bps) — só o patch.
- Todas as versões: [Releases](https://github.com/Ryuuuuuki/FireRed-Encrenca-em-Dobro/releases).


**Um Nuzlocke online para dois jogadores em Pokémon FireRed.** Cada um joga no seu próprio jogo, no seu PC, e toda batalha contra treinador é uma batalha em dupla contra dois clones do treinador.

> ⚠️ **Beta.** Dá para jogar do começo ao fim no que testamos, mas pode ter bugs. Se travar, conte o que estava fazendo (mapa, batalha, captura, bike/surf, emote) e mande um print.

## O que tem
- **Batalhas co-op contra treinadores:** quem encontra o treinador convida, o parceiro aceita e entra. Vocês lutam lado a lado contra dois clones, cada um com metade do time. O rival vem com a versão do time de cada jogador.
- **Modos:** Clássico, Soul Link, Hardcore e Casual, mais as regras da run: primeiro encontro por jogador ou compartilhado, dupes clause, shiny clause, apelidos obrigatórios, level cap, limite de itens em batalha e EXP share.
- **Randomizer (opcional):** selvagens (aleatório ou por tipo), treinadores, habilidades, iniciais e presentes.
- **Dificuldade:** times Vanilla, Difícil ou Elite, com Pokémon de todas as gerações.
- **Jogar junto:** veja o parceiro andando no seu mapa (o "fantasma"), mande emotes, troque Pokémon, mande itens e veja um ao outro no Town Map.
- **Conforto:** relembrador de golpes no resumo do Pokémon (START na página de golpes), texto instantâneo, mapa de encontros por rota e a caixa GRAVES para os que morreram.
- **Recuperação de crash:** quem hospeda volta a run para o último save dos dois.
- **Jessie e James**, da Equipe Rocket, como protagonistas.

## Do que precisa
- **Sua própria ROM** de *Pokémon FireRed (USA, Europe) Rev 1* (`.gba`). O patch só funciona nessa versão (a 1.0 não serve). **Nenhuma ROM é distribuída aqui.**
- Windows (ou Linux, veja o guia do kit).
- Os dois na mesma rede: a Radmin VPN é o mais simples; o Tailscale funciona no Windows e no Linux.
- Quem hospeda precisa do Node.js (LTS) instalado.

## Como jogar (passo a passo)

### 1. Baixe e descompacte o kit
Baixe o **[FireRedDuo_Beta_v0.1.zip](https://github.com/Ryuuuuuki/FireRed-Encrenca-em-Dobro/releases/download/v0.1-beta/FireRedDuo_Beta_v0.1.zip)** e descompacte numa pasta qualquer (por exemplo `Área de Trabalho\FireRedDuo`). Os dois jogadores fazem isso.

### 2. Confira a sua ROM
Você precisa da sua cópia de **Pokémon - FireRed Version (USA, Europe) (Rev 1)**, um arquivo `.gba` de 16 MB. O patch só funciona nessa versão exata. Quando você abrir ela no Rom Patcher JS (próximo passo), ele mostra os códigos de verificação, que precisam bater:

| | |
|---|---|
| CRC32 | `84EE4776` |
| SHA-1 | `DD5945DB9B930750CB39D00C84DA8571FEEBF417` |

Se aparecer outro (por exemplo a versão 1.0, CRC32 `DD88761C`), o jogo não vai funcionar.

### 3. Aplique o patch
1. Abra o **[Rom Patcher JS](https://www.marcrobledo.com/RomPatcher.js/)** (roda no navegador, não precisa instalar).
2. **ROM file:** escolha o seu `.gba` do FireRed e confira o CRC32 (passo 2).
3. **Patch file:** escolha o `FireRedDuo.bps` da pasta do kit.
4. Clique em **Apply patch** e salve o arquivo.
5. Dentro da pasta do kit, crie uma pasta chamada `jogo` e coloque o arquivo nela com o nome **`FireRedDuo.gba`**. Fica `jogo\FireRedDuo.gba`.

### 4. Entrem na mesma rede
1. Os dois instalam a **[Radmin VPN](https://www.radmin-vpn.com/)** (Windows). Com alguém no Linux, usem o **[Tailscale](https://tailscale.com/)** (guia no `LEIA-ME.txt`, passo 9).
2. Quem hospeda cria uma rede (*Rede > Criar rede*); o outro entra (*Rede > Entrar em uma rede existente*).
3. A Radmin mostra o IP de cada um (começa com `26.`).
4. Os dois abrem o `servidor.txt` (na pasta do kit) no Bloco de Notas, trocam o `127.0.0.1` pelo IP da Radmin **de quem hospeda** e salvam.

### 5. Ligue o servidor (só quem hospeda)
1. Instale o **[Node.js](https://nodejs.org)** (versão LTS).
2. Dê dois cliques no `Hospedar_servidor.bat` e deixe a janela aberta enquanto jogam. Se o Windows perguntar sobre acesso à rede, clique em **Permitir**.

### 6. Abra o jogo (os dois)
1. Dê dois cliques no `Jogar.bat`. (Se aparecer "O Windows protegeu o computador", clique em **Mais informações > Executar assim mesmo**.)
2. No mGBA: **Ferramentas > Scripting... > Arquivo > Carregar script...** e escolha `client\duonet.lua`. Deixe a janela de Scripting aberta. Faça isso toda vez que abrir o jogo; nas próximas, use *Arquivo > Carregar script recente*.

### 7. Comecem a run
1. **New Game.** Depois da introdução do Professor Oak, abre o menu **DUO** (também em *Start > DUO*).
2. Um escolhe **Create room**, configura as regras e recebe um código de 6 letras.
3. O outro escolhe **Enter code** e digita o código.
4. A partir daí, toda batalha contra treinador é em dupla: quem encontra o treinador convida, o parceiro aceita.

Mais detalhes (avanço rápido, o que fazer se travar, Linux) no `LEIA-ME.txt` dentro do kit.

## Problemas conhecidos
- **Crashes raros relatados** ("Jumped to invalid address", "OUT OF SPRITE SLOTS"), ainda não reproduzidos. O jogo salva depois de toda batalha e captura; se travar, os dois fecham o jogo e quem hospeda roda o `Voltar_ultimo_ponto.bat` com o código da sala.
- O **VS Seeker não funciona** nesta base.
- No fim de uma batalha co-op, a tela de placar corta nomes longos em 7 letras.
