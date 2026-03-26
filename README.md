# SHERLOCK — Sombras do Funchal: A Ameaça Bloom

Este repositório contém um **jogo textual (CLI)** em Java, onde o jogador assume o papel de **Sherlock Holmes** para investigar o caso “Bloom” no Funchal. O jogo inclui exploração de locais, interação com NPCs, recolha de itens/pistas e progressão por níveis através de deduções.

O ponto de entrada do jogo é `principal.Main` (cria `nucleo.Jogo` e inicia o game loop).

## Funcionalidades

- **Exploração por locais**: mover-te entre áreas e descobrir novas saídas.
- **Interação com NPCs/entidades**: falar, inspecionar, trocar itens.
- **Inventário e pistas**: gerir itens, dinheiro e caderno de notas.
- **Mecânicas de códigos**: inserir códigos em painéis/cofres quando aplicável.
- **Progressão por níveis**: avançar através do comando **deduzir** quando tiveres as pistas necessárias.

## Tecnologias utilizadas

- **Java** (projeto consola)
- **Maven** (build e dependências)

## Requisitos

- **Java 24**: o `pom.xml` está configurado com `maven.compiler.release=24`.
- **Maven**: necessário para compilar.

Para confirmar:

```bash
java -version
mvn -version
```

## Instalação

1. **Clonar o repositório**:

```bash
git clone https://github.com/FGouveia7/JogoSherlockHolmes
```

2. **Entrar na pasta do projeto Maven**:

```bash
cd ProjetoSherlockHolmes
```

3. **Compilar**:

```bash
mvn clean compile
```

## Utilização (executar o jogo)

Na pasta `ProjetoSherlockHolmes`, executa:

```bash
mvn -q clean compile
java -cp target/classes principal.Main
```

- **Windows (PowerShell/CMD)**: o comando acima funciona tal como está.
- **Saída do jogo**: o jogo imprime a introdução e fica a aguardar comandos no terminal.

> Nota: existe a propriedade `exec.mainClass` no `pom.xml`, mas não há configuração de plugin para `mvn exec:java`. Por isso, o método mais direto é executar `principal.Main` via `java -cp`.

## Comandos do jogo

Quando o jogo começar, escreve comandos no terminal:

- **`ir [nome do local]`**: mover-te (ex.: `ir Mercado dos Lavradores`)
- **`olhar`**: ver o que está à tua volta
- **`falar [nome]`**: conversar com um personagem
- **`dar [item] [nome]`**: entregar um item a alguém
- **`usar [item]`**: usar um item do inventário
- **`inspecionar [nome]`**: observar detalhes / apanhar itens
- **`digitar [codigo]`**: inserir códigos em painéis/cofres (quando aplicável)
- **`inventario`**: ver itens e dinheiro
- **`pistas`**: ver o caderno de notas
- **`deduzir`**: tentar resolver o mistério do nível (quando tiveres pistas suficientes)
- **`ajuda`**: listar os comandos novamente
- **`sair`**: fechar o jogo

## Estrutura do projeto

- `ProjetoSherlockHolmes/pom.xml`: configuração Maven
- `ProjetoSherlockHolmes/src/main/java/principal`: ponto de entrada (`Main`)
- `ProjetoSherlockHolmes/src/main/java/nucleo`: loop do jogo, mundo, locais, jogador, inventário
- `ProjetoSherlockHolmes/src/main/java/comandos`: comandos e interpretador (padrão Command)
- `ProjetoSherlockHolmes/src/main/java/itens`: itens, pistas e efeitos
- `ProjetoSherlockHolmes/src/main/java/dialogo`: sistema de diálogo
- `ProjetoSherlockHolmes/src/main/java/entidades`: NPCs/objetos e trocas
- `ProjetoSherlockHolmes/src/main/java/mecanicas`: mecanismos (ex.: códigos)

## Problemas comuns

- **Erro de versão do Java ao compilar**: se o teu Java for inferior a 24, o Maven vai falhar por causa do `maven.compiler.release=24`. Instala/seleciona **JDK 24** e confirma com `java -version`.
- **`target/` a aparecer no git status**: a pasta `ProjetoSherlockHolmes/target/` é gerada pelo Maven (build/javadoc). Em geral, **não deve ser commitada**.

## Contribuição

Sugestões e melhorias são bem-vindas:

- abrir **issues** para bugs/ideias
- criar **pull requests** com melhorias (ex.: novos comandos, balanceamento, mais conteúdo)

## Licença

Projeto para fins educacionais. Sem licença específica definida.

