---
title: Aprovação de Usuário
excerpt: >-
  Este endpoint permite a alteração do status de "aprovação" de um usuário.
  Usuários com status "aprovado" _false_ não podem acessar o sistema.


  Para utilização da rota, será necessário enviar no body o uniqueid daquele
  usuário, conforme payload:


  { "user_uniqueid": "xxxxxxx", "aprovado": false }


  O uniqueid pode ser recuperado na rota /users (Dados de Usuários).


  Importante: esta rota pode ser utilizada apenas por Parceiros Externos.
  Imobiliárias e/ou Franqueadoras devem se utilizar do front do sistema para
  gerirem seus usuários, de forma a garantir atendimento a regras de negócios.
  Usuários com perfil _admin_ do sistema não podem ser desativados via API.
api:
  file: pipeimob-api-pipeimob-v10-1.0.0-resolved.yaml
  operationId: aprovaODeUsuRio
hidden: false
---