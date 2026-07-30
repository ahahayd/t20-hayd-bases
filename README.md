# Tormenta20 — Bases (Heróis de Arton)

Módulo para **FoundryVTT v13** + sistema **Tormenta20** que implementa as regras completas de
**Bases** do capítulo 3 do *Heróis de Arton* (pp. 244-251) como um novo tipo de ator:
**Base — HayD** (independente do suporte nativo do sistema).

## Instalação

Em *Configurar → Módulos Complementares → Instalar Módulo*, cole a URL do manifesto:

```
https://raw.githubusercontent.com/ahahayd/t20-hayd-bases/main/module.json
```

Depois: ative o módulo no mundo e crie um ator do tipo **Base — HayD (Heróis de Arton)**.

## Fluxo de uso

1. **Moradores**: arraste os atores dos personagens (e parceiros/famílias) para a ficha.
   Cada morador tem um interruptor individual para receber ou não os benefícios.
2. **Aba Base**: defina tipo e porte, acompanhe a segurança (composição automática:
   Fortificação +5, Guarita +4, Casa da Guarda +4, Quarto do Capitão +2, Sistema de
   Segurança +4, Domo +2, Gárgulas +2 cada, limitada a 20) e use o **caixa do grupo**
   para custear obras.
3. **Cômodos**: o catálogo completo da Tabela 3-7 com validação de pré-requisitos
   (porte, cômodos, tipo), custo de T$ 1.000 e teste automatizado (CD 20 + cômodos
   que a base pode ter, perícia configurável — padrão Nobreza). Suítes são repetíveis
   e têm atribuição de até 2 moradores; cômodos com escolha (Prateleiras, Capitão)
   são configurados pela engrenagem.
4. **Mobílias**: catálogo da Tabela 3-8, com locais válidos, capacidade por cômodo
   (Sala de Estar comporta 3), gárgulas no exterior (limite por porte) e movimentação
   entre aventuras. Casos especiais automatizados: Ídolo Dourado, Mapa-Múndi, Bigorna,
   Espelho de Corpo, Colchão de Penas, Relíquia Abençoada e Baú Reforçado.
5. **Aventura**: **Iniciar nova aventura** cobra a manutenção (ou danifica um cômodo
   aleatório), lista as escolhas de início de aventura e rola a Ala dos Criados
   (1d4 PM temporários por patamar, por morador). Bases do tipo Empreendimento têm o
   botão de administração (teste de Int + cômodos possíveis → renda em TO).
6. **Homebrews**: crie cômodos e mobílias personalizados (★) com custo, segurança,
   locais válidos e até 4 linhas de Efeitos Ativos usando os caminhos oficiais do
   sistema (com sugestões automáticas, ex.: `system.pericias.luta.bonus`).

## Efeitos Ativos

Os benefícios são distribuídos aos moradores como Efeitos Ativos com os caminhos
oficiais do sistema: `system.pericias.*.bonus` para bônus numéricos de perícia,
`system.pericias.*.treinado` para perícias treinadas, `system.attributes.pv/pm.max`,
`system.attributes.defesa.bonus`, `system.attributes.carga.bonus`,
`system.equipamentos.limiteVestido`, `system.attributes.movement.walk`,
`system.tracos.resistencias.fogo.bonus` e `system.modificadores.*` (valores `+N`).
Benefícios narrativos (Adega, Cozinha, Observatório etc.) aparecem como lembretes.

A sincronização é automática por padrão (configurável) e pode ser disparada
manualmente na aba Base. Ao remover um morador ou excluir a base, os efeitos são
limpos das fichas.

## Aparência

Por padrão a ficha usa o **visual nativo do Foundry VTT v13** (respeitando o tema
claro/escuro do usuário). Se o módulo de tema **t20-hayd-ui** estiver ativo, a ficha
passa automaticamente para o visual *dark glassmorphic* e herda a cor de destaque dele
(cor do dono da ficha ou cor padrão configurável).

## Requisitos

- FoundryVTT **v13**
- Sistema **Tormenta20**
- *(Opcional)* **t20-hayd-ui** para o tema visual combinado

## API

`game.modules.get("t20-hayd-bases").api` (ou `globalThis.tormenta20Bases`) expõe
`catalogo`, `acoes`, `sincronizarEfeitos`, `removerEfeitos`, `montarEfeitosPara`
e `obterMorador` para macros.
