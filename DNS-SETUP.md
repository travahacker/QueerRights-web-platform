# Configuração de Domínios Customizados

Este site está configurado para usar os seguintes domínios:
- **queerrights.codigonaobinario.org** (domínio principal no CNAME)
- **qr.codigonaobinario.org** (domínio secundário via DNS)

## Configuração no GitHub Pages

✅ O arquivo `CNAME` já foi criado com o domínio principal: `queerrights.codigonaobinario.org`

## Configuração DNS

Você precisa configurar os registros DNS no seu provedor de domínio (onde está hospedado `codigonaobinario.org`):

### Para queerrights.codigonaobinario.org (domínio principal)

No painel DNS do seu provedor, adicione um registro **CNAME**:

```
Tipo: CNAME
Nome/Host: queerrights
Valor/Destino: travahacker.github.io
TTL: 3600 (ou padrão)
```

### Para qr.codigonaobinario.org (domínio secundário)

No painel DNS do seu provedor, adicione um registro **CNAME**:

```
Tipo: CNAME
Nome/Host: qr
Valor/Destino: travahacker.github.io
TTL: 3600 (ou padrão)
```

## Configuração no GitHub

1. Acesse: https://github.com/travahacker/QueerRights-web-platform/settings/pages
2. Em "Custom domain", adicione: `queerrights.codigonaobinario.org`
3. Marque "Enforce HTTPS" (será habilitado automaticamente após a propagação DNS)
4. Aguarde a propagação DNS (pode levar de alguns minutos a 48 horas)

## Verificação

Após configurar os DNS, você pode verificar se está funcionando:

```bash
# Verificar o domínio principal
dig queerrights.codigonaobinario.org +short

# Verificar o domínio secundário
dig qr.codigonaobinario.org +short
```

Ambos devem retornar o IP do GitHub Pages (geralmente começa com 185.199.x.x).

## Notas Importantes

- ⚠️ O GitHub Pages permite apenas **um domínio por arquivo CNAME**
- ✅ Ambos os domínios podem apontar para o mesmo site via DNS
- ✅ O domínio `qr.codigonaobinario.org` funcionará automaticamente após configurar o CNAME no DNS
- 🔒 O HTTPS será habilitado automaticamente após a propagação DNS

