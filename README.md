# T20 Hayd Bases (Heróis de Arton)

Implementa as regras completas de **Bases** do capítulo 3 do *Heróis de Arton* (pp. 244–251) no FoundryVTT como um novo tipo de ator: portes, tipos, segurança, manutenção, cômodos, mobílias e moradores recebendo os benefícios automaticamente.

## Requisitos

- FoundryVTT **v13**
- Sistema **Tormenta20**
- *(Opcional)* **t20-hayd-ui** — a ficha adota o tema visual combinado quando ativo

## Instalação

Em *Configurar → Módulos Complementares → Instalar Módulo*, cole a URL do manifesto:

```
https://github.com/ahahayd/t20-hayd-bases/releases/latest/download/module.json
```

Depois de ativar, crie um ator do tipo **Base — HayD (Heróis de Arton)**.

## Como usar

### Moradores

Arraste os atores dos personagens (e parceiros) para a ficha da base. Cada morador tem um interruptor individual para receber ou não os benefícios, que são aplicados como Efeitos Ativos nas fichas — bônus de perícia, PV/PM, Defesa, carga e afins. Benefícios narrativos aparecem como lembretes.

### Aba Base

Defina o tipo e o porte, acompanhe a **segurança** (composta automaticamente pelos cômodos e mobílias, limitada a 20) e use o caixa do grupo para custear as obras.

### Cômodos e mobílias

Catálogos completos das Tabelas 3-7 e 3-8, com validação de pré-requisitos (porte, tipo, cômodos), custo e teste de construção automatizado. Suítes são repetíveis com atribuição de moradores, mobílias respeitam os locais válidos e a capacidade de cada cômodo, e os casos especiais (Ídolo Dourado, Mapa-Múndi, Bigorna, Baú Reforçado…) são automatizados.

### Entre aventuras

**Iniciar nova aventura** cobra a manutenção (ou danifica um cômodo aleatório), lista as escolhas de início de aventura e rola a Ala dos Criados. Bases do tipo Empreendimento têm o botão de administração, que faz o teste e gera a renda em TO.

### Homebrews

Crie cômodos e mobílias personalizados (★) com custo, segurança, locais válidos e Efeitos Ativos usando os caminhos oficiais do sistema, com sugestões automáticas de preenchimento.

## Detalhes adicionais

- A sincronização dos efeitos com os moradores é automática por padrão (configurável) e pode ser disparada manualmente; ao remover um morador ou excluir a base, os efeitos são limpos das fichas.
- API para macros em `game.modules.get("t20-hayd-bases").api`: `catalogo`, `acoes`, `sincronizarEfeitos`, `removerEfeitos`, `montarEfeitosPara` e `obterMorador`.

## Aviso

Módulo não oficial, criado por fã, sem afiliação com a Jambô Editora ou com os autores de Tormenta20.
