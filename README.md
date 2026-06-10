# Diagramas de Entidade-Relacionamento (DER)

Este repositório contém diagramas de Entidade-Relacionamento criados para fins de estudo e prática de **Modelagem de Banco de Dados**.  
O foco principal é compreender **cardinalidade** — ou seja, quantos registros de uma entidade podem se relacionar com registros de outra entidade (1:1, 1:N, N:N).  
Os diagramas foram desenvolvidos utilizando **Draw.io** e representam diferentes cenários.

---

## 🧑 Diagrama: Pessoa - Certidão de Nascimento (Exemplo de 1:1)

### Entidades
- **Pessoa**
  - PK: `CPF`
  - Atributos: `nome`, `data_nascimento`

- **Certidão_Nascimento**
  - PK: `id_certidao`
  - FK: `CPF`
  - Atributos: `cartorio`, `data_emissao`

### Relacionamento
- Cada **Pessoa** possui exatamente uma **Certidão de Nascimento**.  
- Cada **Certidão de Nascimento** corresponde a exatamente uma **Pessoa**.  
- Esse é um relacionamento **1:1 (um-para-um)**, representado pela FK `CPF` na entidade **Certidão_Nascimento**.

---

## 👤 Diagrama: Usuário - Evento (Exemplo de 1:N)

### Entidades
- **Usuário**
  - PK: `CPF_usuario`
  - Atributos: `nome`, `data_nascimento`

- **Evento**
  - PK: `id_evento`
  - FK: `CPF_usuario`
  - Atributos: `nome`, `data`

### Relacionamento
- Um **Usuário** pode estar associado a vários **Eventos**.  
- Cada **Evento** pertence a exatamente um **Usuário**.  
- Esse é um relacionamento **1:N (um-para-muitos)**, representado pela FK `CPF_usuario` na entidade **Evento**.

---

## 🎵 Diagrama: Música - Playlist (Exemplo de N:N)

### Entidades
- **Música**
  - PK: `id_musica`
  - Atributos: `nome_musica`, `artista`, `data_lançamento`

- **Playlist**
  - PK: `nome_playlist`
  - Atributos: `data_criacao`

- **Tabela_Associativa**
  - PK: `id_tba`
  - FK: `id_musica`
  - FK: `nome_playlist`

### Relacionamento
- Uma **Música** pode estar em várias **Playlists**.  
- Uma **Playlist** pode conter várias **Músicas**.  
- Esse é um relacionamento **N:N (muitos-para-muitos)**, que é resolvido pela **Tabela_Associativa**, responsável por armazenar as combinações entre músicas e playlists.

---

## 📌 Observações
- O diagrama **Pessoa–Certidão de Nascimento** demonstra como modelar relacionamentos **um-para-um (1:1)**.  
- O diagrama **Usuário–Evento** demonstra como modelar relacionamentos **um-para-muitos (1:N)**, colocando a chave estrangeira no lado "N".  
- O diagrama **Música–Playlist** demonstra como modelar relacionamentos **muitos-para-muitos (N:N)**, utilizando uma tabela associativa.  

Esses exemplos são úteis para compreender os conceitos de **modelagem de banco de dados** e **cardinalidade**, servindo como base para implementação em SQL.

**Esse repositório é gradualmente atualizado e melhorado.**

⭐ Projeto desenvolvido por **Mariana B. Teixeira**
