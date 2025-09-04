---
title: Negócios Detalhados
excerpt: >-
  Rota para retornar detalhes sobre todas as transações. É obrigatório que se
  passe um range de datas, que deverá ser de no máximo 31 dias. As datas levam
  em consideração a assinatura do compromisso de compra e venda.


  ### **Filtros e Configurações da Rota de Negócios**


  Por padrão, os campos "date_initial" e "date_final" dizem respeito às datas de
  assinatura dos CCVs.


  Porém, caso se queira mandar tal range relativamente à data do "início" da
  venda (término do preenchimento do Formulário de Transação e envio do imóvel à
  tela de Negócios), basta se mandar o campo adicional abaixo no body da
  requisição:


  _"date_type": "venda_inicio"_


  Caso se queira retornar um negócio específico, então basta mandar um dos
  seguintes campos no _body_:


  _"codigo_imovel": "XPTO"_


  ou


  _"codigo_contrato": "XPTO"_


  ou


  _"transacao_uniqueid": "transacao_uniqueid"_


  Atenção: caso sejam mandado os campos "codigo_imovel" ou "codigo_contrato" ou
  "transacao_uniqueid", então a API não levará em consideração o "date_initial",
  "date_final" e o "date_type". E, caso mais de um filtro (dentre
  "codigo_imovel" ou "codigo_contrato" ou "transacao_uniqueid" sejam mandados na
  mesma requisição, apenas um deles será considerado, com a seguinte ordem de
  preferência:


  "transacao_uniqueid": maior prioridade


  "codigo_contrato": priodidade média


  "codigo_imovel": menor prioridade


  ### **Negócios de outras imobiliárias nas quais se é comissionado**


  A /negocios, por padrão, retorna as transações que pertencem à imobiliária (ou
  às imobiliárias da franquia) - ou seja, aquelas cuja esteira da venda está
  sendo liderada pela mesma. Porém, é possível também recuperar as transações de
  outras imobiliárias (ou, no caso de franquias, de imobiliárias que não
  pertencem à rede) que incluíram a sua como comissionada, no formulário de
  transação.


  Para isto, basta passar o campo abaixo no body:


  _"comissionado_externo": yes_


  Desta forma, serão retornados os negócios de outras imobiliárias que,
  respeitados os outros filtros enviados (date_initial, date_final, date_type),
  incluíram aquela na estrutura de comissionados.


  Este filtro (de _comissionado_externo_) está disponível apenas para usuários
  da API que representem imobiliárias ou franquias, mas não para perfis de
  Parceiros Externos.


  ### **Filtro de uma transação específica**


  Caso se opte por recuperar os detalhes de uma transação única (utilizando-se
  os filtros "transacao_uniqueid", "codigo_contrato" ou "codigo_imovel"), o json
  devolvido conterá detalhes adicionais sobre aquele negócio:


  - relação das subetapas da esteira, com status (Desativada, Em Andamento, Em
  Atenção ou Concluída)
      
  - para as subetapas que não estiverem Desativadas:
      
      - eventuais tarefas que são previstas para aquela subetapa, com seu tipo ("Resposta Digitada", "Uma Opção", "Checklist" ou "Anexar Arquivos") e a pergunta em si
          
      - para as tarefas respondidas:
          
          - quando foi respondida
              
          - quem respondeu
              
          - detalhes da resposta (em caso de "Anexar Arquivos" ou "Checklist", os detalhes serão uma _lista_)
api:
  file: pipeimob-api-pipeimob-v10-1.0.0-resolved.yaml
  operationId: negCiosDetalhados
hidden: false
---