---
title: Auth
excerpt: >-
  # Autenticação e Autorização


  - Para utilizar os recursos da **API PIPEIMOB** é preciso primeiro se
  autenticar através desse endpoint &#96;/Auth&#96; para obter o token.

  - Através desse processo, após verificação das credenciais, a plataforma irá
  devolver um Token (token) o quel deverá ser utilizado em todas as chamadas aos
  demais endpoints..
      

  ## Credenciais


  Primeira ação realizada é a autenticação. Essa chamada solicita os seguintes
  parâmetros:


  | Parâmetro | Descrição |

  | --- | --- |

  | api_key | a API_KEY é uma UUID padrão universal (string no formato formato
  00000000-0000-0000-0000-000000000000 tipo texto, única e imutável), enviado ao
  usuário da plataforma PIPEIMOB durante o cadastro. Essa informação pode ser
  encontrada no Pipeimob clicando em INTEGRAÇÕES, na seção API PIPEIMOB. |

  | api_secret | A API_SECRET é uma string codificadoa SHA256, tipo texto, com
  32 caracteres. É enviada para o usuário no ato de abertura de conta. Essa
  informação pode ser encontrada no Pipeimob clicando em INTEGRAÇÕES, na seção
  API PIPEIMOB. |


  ---


  Confira na imagem abaixo o fluxo de autenticação da **API PIPEIMOB** versão
  1.0:




  Em **todos os casos,** de sucesso ou insucesso, a **resposta sempre será tipo
  200 OK**, porém no corpo da mensagem de resposta, o campo &#34;status&#34;
  trará detalhes, informando se a autenticação ocorreu com sucesso ou se falhou.
api:
  file: pipeimob-api-pipeimob-v10-1.0.0-resolved.yaml
  operationId: auth
hidden: false
---