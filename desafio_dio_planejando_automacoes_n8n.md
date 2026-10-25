# Desafio Criativo DIO — Planejando Automações com n8n Usando Apenas Bons Prompts

## Passo 1 — Defina a automação desejada

**Processo:** envio automático de lembretes de cobrança antes do vencimento.

**Público ou responsável:** equipe financeira e clientes com cobranças pendentes.

**Resultado esperado:** consultar uma planilha de cobranças, identificar pagamentos próximos do vencimento e enviar lembretes personalizados por e-mail, registrando o envio para evitar duplicidade.

## Passo 2 — Adicione contexto e regras

**Ferramentas envolvidas:** n8n, Google Sheets e Gmail.

**Fluxo desejado:**

1. Executar o workflow diariamente em horário definido.
2. Consultar no Google Sheets os dados das cobranças, incluindo cliente, e-mail, valor, vencimento, status e data do último lembrete.
3. Verificar quais cobranças estão pendentes e vencem nos próximos três dias.
4. Validar se o e-mail do cliente está preenchido e apresenta formato válido.
5. Verificar se ainda não foi enviado lembrete para aquela cobrança no dia atual.
6. Enviar pelo Gmail um lembrete personalizado com cliente, valor e vencimento.
7. Atualizar na planilha a data do último lembrete e o resultado do envio.

**Regras importantes:**

- Não enviar lembretes de cobranças com status **PAGO**.
- Ignorar registros sem e-mail válido e registrar a ocorrência para revisão.
- Não enviar mais de um lembrete por cobrança no mesmo dia.
- Considerar apenas cobranças com vencimento entre a data atual e os próximos três dias, inclusive.
- Em caso de falha no envio, registrar o erro sem marcar o lembrete como enviado.
- Utilizar dados de exemplo durante os testes e manter as credenciais protegidas no n8n.

## Passo 3 — Prompt final

> Atue como um especialista em n8n e em automação de processos financeiros.
>
> Crie o planejamento de uma automação para enviar lembretes de cobrança por e-mail antes do vencimento.
>
> **Público:** equipe financeira e clientes com cobranças pendentes.
>
> **Ferramentas envolvidas:** n8n, Google Sheets e Gmail.
>
> **Fluxo:**
> 1. Iniciar automaticamente todos os dias em um horário configurável.
> 2. Ler uma planilha do Google Sheets com os campos `id_cobranca`, `nome_cliente`, `email`, `valor`, `data_vencimento`, `status` e `data_ultimo_lembrete`.
> 3. Selecionar apenas cobranças pendentes com vencimento entre hoje e os próximos três dias.
> 4. Validar o e-mail e verificar se a cobrança ainda não recebeu lembrete hoje.
> 5. Enviar um e-mail personalizado com o nome do cliente, valor e data de vencimento.
> 6. Atualizar a planilha com a data do envio e seu resultado.
>
> **Regras:**
> - Não enviar mensagens para cobranças pagas.
> - Ignorar e registrar registros sem e-mail válido.
> - Evitar mensagens duplicadas para a mesma cobrança no mesmo dia.
> - Registrar erros de envio e não marcar como enviado quando houver falha.
> - Tratar corretamente as datas e o fuso horário da execução.
> - Usar credenciais seguras para Google Sheets e Gmail.
>
> **Instruções para sua resposta:**
> - Indique quais nodes do n8n devem ser utilizados e a função de cada um.
> - Explique a ordem de conexão dos nodes e a lógica de funcionamento do workflow.
> - Descreva as condições de filtragem, validação, envio e atualização da planilha.
> - Apresente exemplos de dados de entrada e do resultado esperado.
> - Inclua sugestões para testar o fluxo e tratar erros antes de colocá-lo em produção.
> - Caso algum detalhe técnico dependa da versão do n8n ou das permissões do Google, destaque o que deve ser verificado.

## Entrega na DIO

Este arquivo documenta o planejamento e o prompt final solicitados no desafio criativo. Ele não representa, por si só, um workflow implementado ou testado.

Para entregar: publique este arquivo `.md` em um repositório público do GitHub ou no Google Drive com acesso por link e cole a URL da página do arquivo no campo de submissão da DIO.
