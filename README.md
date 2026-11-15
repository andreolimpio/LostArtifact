# 🎮 Lost Artifact

**Lost Artifact** é um jogo 3D de aventura, exploração e combate desenvolvido com **Unity e C#**, criado como parte de um conjunto de ativos acadêmicos voltados ao ensino e à prática de desenvolvimento de software e jogos digitais.

O projeto tem como objetivo reunir, em uma aplicação prática, diferentes conceitos de desenvolvimento de jogos, como movimentação de personagens, inteligência artificial, máquinas de estados, HUD, colisões, animações, gerenciamento de cenas, condições de vitória e derrota, entre outros.

---

## 📖 Sobre o jogo

Em **Lost Artifact**, o jogador assume o controle de um personagem que precisa explorar diferentes ambientes em busca das partes de um antigo artefato perdido.

Durante sua jornada, o jogador deverá atravessar diferentes cenários, enfrentar inimigos, sobreviver a criaturas perigosas, superar obstáculos e localizar os fragmentos espalhados pelo mundo.

Cada cenário possui um fragmento do artefato.

Ao encontrar todas as partes, o jogador poderá finalmente reconstruir o **Lost Artifact** e concluir sua missão.

---

## 🗺️ Progressão do jogo

A estrutura inicial do jogo prevê entre três e quatro cenários diferentes.

A progressão conceitual ocorre da seguinte forma:

```text
Início
   ↓
Cenário 01
   ↓
Exploração + Inimigos + Obstáculos
   ↓
Fragmento 01
   ↓
Cenário 02
   ↓
Exploração + Novos desafios
   ↓
Fragmento 02
   ↓
Cenário 03
   ↓
Exploração + Combate + Obstáculos
   ↓
Fragmento 03
   ↓
Cenário 04
   ↓
Desafio final
   ↓
Fragmento 04
   ↓
Reconstrução do artefato
   ↓
Vitória
```

---

## 🌎 Cenários

A proposta inicial prevê ambientes com características diferentes, permitindo que novas mecânicas sejam introduzidas progressivamente.

Entre os cenários planejados estão:

- Ruínas;
- Floresta;
- Cavernas;
- Templo ou cenário final.

Cada ambiente poderá possuir inimigos, obstáculos, ambientação, desafios e mecânicas próprias.

---

## 🧍 Player

O personagem principal será controlado pelo jogador em um ambiente tridimensional.

Entre suas principais funcionalidades estão:

- movimentação;
- rotação;
- corrida;
- salto;
- sistema de vida;
- recebimento de dano;
- combate;
- interação com objetos;
- coleta de itens;
- animações;
- detecção de colisões;
- interação com o ambiente.

O desenvolvimento do Player será estruturado utilizando componentes separados para diferentes responsabilidades.

Exemplo:

```text
Player
├── PlayerController
├── PlayerMovement
├── PlayerInput
├── PlayerHealth
├── PlayerCombat
├── PlayerInteraction
└── PlayerAnimation
```

---

## 👹 Inimigos

O jogo poderá apresentar diferentes tipos de inimigos durante a exploração dos cenários.

Entre eles:

- zumbis;
- animais hostis;
- criaturas;
- inimigos especiais.

Cada inimigo poderá possuir comportamentos diferentes de movimentação, patrulha, detecção, perseguição e ataque.

---

## 🤖 Inteligência Artificial

A Inteligência Artificial será um dos principais conceitos abordados no projeto.

Os inimigos poderão utilizar comportamentos como:

```text
Idle
  ↓
Patrol
  ↓
Detect Player
  ↓
Chase
  ↓
Attack
```

Outros estados poderão ser adicionados posteriormente:

```text
Search
Hurt
ReturnToPatrol
Dead
```

A implementação poderá utilizar recursos como:

- NavMesh;
- NavMesh Agent;
- sensores de percepção;
- distância de detecção;
- distância de ataque;
- linha de visão;
- máquinas de estados.

---

## 🔄 Máquina de Estados

Os comportamentos dos inimigos serão organizados utilizando o padrão **State Machine**.

Uma estrutura possível será:

```text
Enemy
  │
  ├── Idle
  │
  ├── Patrol
  │
  ├── Chase
  │
  ├── Attack
  │
  ├── Hurt
  │
  └── Dead
```

O objetivo é manter os comportamentos desacoplados e facilitar a evolução da Inteligência Artificial.

---

## 🗿 Sistema do Artefato

A principal mecânica de progressão está relacionada à coleta dos fragmentos do artefato.

Cada cenário deverá possuir uma parte do objeto.

Exemplo:

```text
Fragmento 01
Fragmento 02
Fragmento 03
Fragmento 04
```

O sistema será responsável por:

- identificar fragmentos encontrados;
- registrar a progressão;
- atualizar o HUD;
- controlar a conclusão dos cenários;
- verificar a condição de vitória;
- reconstruir o artefato ao final da aventura.

---

## ❤️ HUD

O jogo possuirá uma interface responsável por apresentar informações importantes ao jogador.

Entre os elementos previstos:

- barra de vida;
- quantidade de fragmentos encontrados;
- objetivo atual;
- mensagens de interação;
- indicação de dano;
- informações da fase.

Exemplo:

```text
Vida: ████████░░ 80/100

Fragmentos: 2/4

Objetivo:
Encontre o próximo fragmento do artefato.
```

---

## ⚔️ Sistema de combate

O projeto poderá implementar um sistema básico de combate entre o jogador e os inimigos.

Entre os conceitos previstos:

- ataque;
- dano;
- vida;
- morte;
- alcance;
- colisões;
- animações;
- interfaces para objetos que recebem dano.

Uma possível abstração será:

```text
IDamageable
     │
     ├── Player
     │
     └── Enemy
```

Isso permite que diferentes objetos utilizem o mesmo contrato para receber dano.

---

## 🧱 Obstáculos e ambiente

Além dos inimigos, o jogador deverá enfrentar desafios existentes no próprio cenário.

Entre os possíveis elementos:

- armadilhas;
- plataformas;
- áreas perigosas;
- obstáculos físicos;
- portas;
- passagens bloqueadas;
- objetos interativos;
- checkpoints.

---

## 🎬 Gerenciamento de cenas

Os diferentes ambientes do jogo serão organizados utilizando o sistema de cenas da Unity.

Uma estrutura inicial poderá utilizar:

```text
Boot
MainMenu
Prologue
Level01
Level02
Level03
Level04
Ending
```

O projeto também poderá possuir:

- tela de carregamento;
- transição entre fases;
- persistência de informações;
- controle de progressão.

---

## 🏆 Condição de vitória

A condição principal de vitória será encontrar todos os fragmentos necessários para reconstruir o artefato.

```text
Todos os fragmentos encontrados?
           │
      ┌────┴────┐
      │         │
     Não       Sim
      │         │
Continua    Artefato
            reconstruído
                │
              Vitória
```

---

## 💀 Condição de derrota

A principal condição de derrota será relacionada à vida do jogador.

Exemplo:

```text
PlayerHealth <= 0
        ↓
     Game Over
```

Novas condições poderão ser adicionadas futuramente de acordo com a evolução do projeto.

---

## 🛠️ Tecnologias

O projeto utiliza ou poderá utilizar as seguintes tecnologias e ferramentas:

- **Unity**
- **C#**
- Unity Input System
- Unity Animator
- Unity NavMesh
- Unity Physics
- Unity UI
- Cinemachine
- Visual Studio / Visual Studio Code
- Git
- GitHub

---

## 📚 Conceitos abordados

O Lost Artifact foi estruturado para permitir o estudo e a aplicação prática de diferentes conceitos relacionados ao desenvolvimento de jogos.

Entre eles:

- GameObjects;
- Components;
- Prefabs;
- Scenes;
- C#;
- Programação Orientada a Objetos;
- encapsulamento;
- interfaces;
- composição;
- movimentação 3D;
- física;
- colisões;
- triggers;
- animações;
- HUD;
- UI;
- sistema de vida;
- sistema de dano;
- combate;
- Inteligência Artificial;
- NavMesh;
- máquinas de estados;
- gerenciamento de cenas;
- transição entre fases;
- interação com objetos;
- coleta de itens;
- condições de vitória;
- condições de derrota;
- Game Loop;
- ScriptableObjects;
- gerenciamento de assets.

---

## 📁 Estrutura do projeto

A organização principal do repositório segue a estrutura recomendada para projetos Unity.

```text
LostArtifact/
│
├── Assets/
│   │
│   ├── _LostArtifact/
│   │   ├── Animations/
│   │   ├── Art/
│   │   ├── Audio/
│   │   ├── Input/
│   │   ├── Materials/
│   │   ├── Models/
│   │   ├── Prefabs/
│   │   ├── Scenes/
│   │   ├── ScriptableObjects/
│   │   ├── Settings/
│   │   ├── UI/
│   │   ├── VFX/
│   │   │
│   │   └── Scripts/
│   │       ├── AI/
│   │       ├── Artifact/
│   │       ├── Audio/
│   │       ├── Combat/
│   │       ├── Core/
│   │       ├── Enemy/
│   │       ├── Environment/
│   │       ├── GameFlow/
│   │       ├── Interaction/
│   │       ├── Player/
│   │       ├── Save/
│   │       ├── SceneManagement/
│   │       ├── StateMachine/
│   │       ├── UI/
│   │       └── Utilities/
│   │
│   ├── ThirdParty/
│   └── Plugins/
│
├── Packages/
├── ProjectSettings/
│
├── docs/
│   ├── architecture/
│   ├── assets/
│   ├── development/
│   ├── diagrams/
│   ├── gameplay/
│   ├── roadmap/
│   └── teaching/
│
├── screenshots/
├── builds/
│
├── .github/
├── .gitignore
├── .gitattributes
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

---

## 📦 Assets externos

O projeto poderá utilizar modelos, animações, texturas, efeitos sonoros, cenários e outros recursos provenientes de fontes externas, incluindo a **Unity Asset Store**.

Esses recursos estarão sujeitos às respectivas licenças de seus autores e distribuidores.

Assets comerciais ou que não possam ser redistribuídos publicamente não serão necessariamente disponibilizados neste repositório.

As referências e informações relacionadas aos recursos utilizados deverão ser registradas na documentação do projeto.

---

## 🔀 Versionamento

O desenvolvimento utilizará Git e GitHub para controle de versão.

A estratégia de branches poderá utilizar:

```text
main
develop
feature/*
fix/*
```

Exemplos:

```text
feature/player-movement
feature/player-health
feature/zombie-ai
feature/hud
feature/artifact-system
feature/level-01
```

---

## 🏷️ Versionamento do projeto

As versões poderão seguir o padrão de Versionamento Semântico:

```text
MAJOR.MINOR.PATCH
```

Exemplo:

```text
v0.1.0
v0.2.0
v0.5.0
v1.0.0
```

A versão `1.0.0` representará a primeira versão considerada completa e jogável do projeto.

---

## 🛣️ Roadmap

### Etapa 01 — Estrutura inicial

- [ ] Criação do projeto Unity
- [ ] Configuração do Git
- [ ] Estrutura de diretórios
- [ ] Configuração do Input System
- [ ] Configuração inicial da câmera

### Etapa 02 — Player

- [ ] Movimentação
- [ ] Corrida
- [ ] Salto
- [ ] Animações
- [ ] Sistema de vida
- [ ] Sistema de interação

### Etapa 03 — Gameplay

- [ ] HUD
- [ ] Sistema de dano
- [ ] Colisões
- [ ] Obstáculos
- [ ] Interações

### Etapa 04 — Inimigos

- [ ] Primeiro inimigo
- [ ] Sistema de vida
- [ ] Sistema de ataque
- [ ] Animações

### Etapa 05 — Inteligência Artificial

- [ ] NavMesh
- [ ] Patrulha
- [ ] Detecção do jogador
- [ ] Perseguição
- [ ] Ataque
- [ ] Máquina de estados

### Etapa 06 — Artefato

- [ ] Sistema de fragmentos
- [ ] Coleta
- [ ] Atualização do HUD
- [ ] Controle de progressão
- [ ] Reconstrução final

### Etapa 07 — Cenários

- [ ] Cenário 01
- [ ] Cenário 02
- [ ] Cenário 03
- [ ] Cenário 04

### Etapa 08 — Finalização

- [ ] Menu principal
- [ ] Pause
- [ ] Game Over
- [ ] Tela de vitória
- [ ] Áudio
- [ ] Efeitos visuais
- [ ] Polimento
- [ ] Build
- [ ] Documentação final

---

## 🎓 Objetivo acadêmico

Além de ser um jogo, o **Lost Artifact** é um projeto acadêmico criado para servir como laboratório prático de desenvolvimento de jogos digitais.

O projeto poderá ser utilizado como referência para estudos e aulas envolvendo:

- desenvolvimento de jogos com Unity;
- programação C#;
- arquitetura de software aplicada a jogos;
- orientação a objetos;
- Inteligência Artificial;
- máquinas de estados;
- desenvolvimento de interfaces;
- gerenciamento de cenas;
- integração entre programação, arte e gameplay.

O objetivo é permitir que novos conceitos sejam adicionados progressivamente, mantendo uma arquitetura organizada e facilitando sua utilização como material didático.

---

## 🚧 Status do projeto

> **Em desenvolvimento.**

O projeto encontra-se em fase de planejamento e implementação incremental.

As funcionalidades serão adicionadas progressivamente de acordo com o roadmap.

---

## 👨‍💻 Autor

Projeto desenvolvido por **André Olímpio**.

Professor de Tecnologia da Informação e desenvolvedor de projetos acadêmicos voltados ao ensino de programação, banco de dados, engenharia de software, Inteligência Artificial e desenvolvimento de jogos digitais.

---

## 📄 Licença

O código-fonte desenvolvido especificamente para este projeto estará sujeito à licença definida neste repositório.

Assets, modelos, animações, músicas, efeitos sonoros, fontes, texturas e outros recursos de terceiros permanecem sujeitos às licenças de seus respectivos autores e distribuidores.

---

**Lost Artifact**  
*Explore. Sobreviva. Encontre os fragmentos. Reconstrua o que foi perdido.*
