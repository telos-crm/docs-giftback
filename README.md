# Telos Giftback API - Documentação V1

Documentação pública da API Giftback (V1 default — fluxo padrão para integração com ERP/PDV).

## 🔗 Acesso

- **Documentação**: https://docs-giftback.telosdigital.app.br
- **API Produção**: https://giftback.teloscrm.com.br/api/v1
- **API Homologação**: https://giftback.hom.teloscrm.com.br/api/v1

## 📋 Endpoints Disponíveis

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| POST | `/auth` | Autenticação - obtém access_token e refresh_token |
| POST | `/refresh` | Renovação de token |
| POST | `/user/verify` | Verifica/cria cliente por CPF |
| POST | `/pin/send` | Envio de PIN por SMS |
| POST | `/pin/validate` | Validação do PIN |
| POST | `/pin/resend` | Reenvio do PIN |
| POST | `/bonus/balance` | Consulta saldo do cliente (sem dados de venda) |
| POST | `/bonus/available` | Consulta saldo disponível para a compra |
| POST | `/bonus/campaigns` | Consulta campanhas aplicáveis |
| POST | `/bonus/submit` | Confirma uso de bônus |
| POST | `/sales/total` | Totaliza venda e gera bônus |
| POST | `/sales/cancel` | Cancela venda e estorna bônus |

## 🔐 Autenticação

A API usa JWT Bearer Token. Obtenha o token via `/auth`:

```bash
curl -X POST https://giftback.teloscrm.com.br/api/v1/auth \
  -H "Content-Type: application/json" \
  -d '{"username": "SEU_CLIENT_ID", "password": "SEU_CLIENT_SECRET"}'
```

Use o `access_token` retornado no header `Authorization: Bearer {token}`.

## 📞 Suporte

- Email: diego.dias@teloscrm.com.br
- Site: https://telosdigital.app.br

## 🔄 Atualização

O `openapi.json` é sincronizado automaticamente do repo privado `telos-crm` em todo merge na branch `production`. **Não edite manualmente** — qualquer mudança será sobrescrita no próximo sync.
