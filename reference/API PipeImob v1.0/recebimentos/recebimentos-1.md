---
title: Recebimentos
excerpt: >-
  Esta rota permite consultar, de forma estruturada, **todas as cobranças do
  tipo Comissões que já foram pagas (liquidadas)** dentro de um determinado
  período de tempo.


  Ela é utilizada por imobiliárias e franqueadoras para obter uma **visão
  consolidada dos valores recebidos**, seja por um **usuário específico** ou por
  um **grupo (equipe, unidade ou filial)**.

    
  Na prática, ela serve para responder perguntas como:


  - **“Quais comissões eu recebi neste mês?”**
      
  - **“Quais cobranças geridas pela minha unidade já foram pagas?”**
      
  - **“Quanto cada pessoa da equipe recebeu em um determinado período?”**
      

    
  O retorno inclui os valores totais recebidos, os dados da cobrança, o cliente
  pagador, e a **estrutura completa do split** — detalhando quanto cada
  favorecido recebeu, em qual conta e sob qual rede.


  Disponível apenas para **imobiliárias** ou **franqueadoras** integradas ao
  PipeImob.


  ### **Parâmetros obrigatórios**


  - dateFrom: data e hora inicial do período (**formato: YYYY-MM-DD HH:mm:ss**)
      
  - dateTo: data e hora final do período (**formato: YYYY-MM-DD HH:mm:ss**)
      

  Além do período, é necessário informar um **filtro de escopo**:


  - user: e-mail de um usuário (traz cobranças em que ele aparece como
  **favorecido no split**)
      
  - grupo: slug do grupo (traz cobranças liquidadas geridas por **usuários
  vinculados a esse grupo**)
      

  **Importante:** envie **apenas um dos dois filtros** (user ou grupo) por vez.


  ### **Observações**


  - O campo user espera o **e-mail completo** do usuário.
      
  - O campo grupo espera o **slug configurado da unidade ou grupo**.
      
      \- Caso não saiba o slug, entre em contato com o suporte do PipeImob.
      
  - A rota considera **apenas cobranças liquidadas** com tipo "Comissões".
      

  - A resposta inclui:
      
      - Número total de cobranças
          
      - Valor total recebido
          
      - Lista detalhada de cada cobrança com seus splits
api:
  file: pipeimob-api-pipeimob-v10-1.0.0-resolved.yaml
  operationId: recebimentos
hidden: false
---