
# 🤖 Triagem Inteligente de Suporte com IA (n8n + Google Gemini)

Sistema automatizado de classificação, priorização e roteamento de tickets/e-mails de suporte utilizando **n8n**, **Google Gemini**, **Google Sheets** e **Gmail**.

## 🎯 Problema Resolvido
Equipas de atendimento perdem tempo crítico a ler e triar manualmente pedidos de suporte, o que atrasa a resposta a incidentes graves (como falhas de pagamento ou quedas de sistema). Esta automação lê cada pedido recebido, identifica a urgência e a categoria técnica em segundos, regista tudo numa base de dados centralizada e alerta imediatamente a equipa quando há um caso crítico.

## 🏗️ Arquitetura do Fluxo

```text
[Webhook POST] ──▶ [Google Gemini (Análise IA)] ──▶ [Code JS (Parse JSON)] ──▶ [Google Sheets (Log)]
                                                                                     │
                                                                                     ▼
                                                                             [IF: Urgência == Alta?]
                                                                                │              │
                                                                               Sim            Não
                                                                                │              │
                                                                                ▼              ▼
                                                                        [Gmail: Alerta]     (Fim)
