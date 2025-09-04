---
title: Lista de Negócios
excerpt: >-
  Esta rota retornará a lista de transações que estão em curso, assim como
  aquelas que foram já arquivadas.


  O retorno contempla somente o uniqueID de cada transação, cujos detalhes
  poderão ser recuperados na rota própria.


  É obrigatório o envio no _body_ do filtro especificando a data da última
  modificação naquela transação - ou seja, deve-se retornar apenas transações
  cujos registros tiveram alguma (qualquer) alteração posteriormente à data
  selecionada, conforme modelo:


  {"date_last_modified": "AAAA-MM-DD hh:mm:ss"}


  No caso do usuário da API ter perfil de "imobiliária", serão retornadas as
  transações da mesma, assim como aquelas nas quais tal imobiliária foi incluída
  como comissionada.


  No caso do usuário da API ter perfil de "franquia", serão retornadas as
  transações de todas as imobiliárias de tal rede, assim como aquelas nas quais
  tais imobiliárias foram incluídas como comissionadas.


  No caso do usuário da API ter o perfil de "parceiro", serão retornadas as
  transações que incluíram tal parceiro como envolvido, assim como toas as
  transações de imobiliárias que deram autorização total a acesso a dados via
  API àquele parceiro.
api:
  file: pipeimob-api-pipeimob-v10-1.0.0-resolved.yaml
  operationId: listaDeNegCios
hidden: false
---