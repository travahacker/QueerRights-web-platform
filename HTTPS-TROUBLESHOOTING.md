# Troubleshooting HTTPS - Domínio Customizado

## Problema: "Enforce HTTPS — Unavailable"

Isso acontece quando o GitHub Pages ainda não conseguiu verificar e configurar o certificado SSL para seu domínio.

## Passos para Resolver

### 1. Verificar Configuração DNS

Certifique-se de que o DNS está configurado corretamente:

```bash
# Verificar se o CNAME está apontando corretamente
dig queerrights.codigonaobinario.org CNAME +short
# Deve retornar: travahacker.github.io.

# Verificar se resolve para os IPs do GitHub
dig queerrights.codigonaobinario.org +short
# Deve retornar IPs começando com 185.199.x.x
```

### 2. Verificar no GitHub Pages

1. Acesse: https://github.com/travahacker/QueerRights-web-platform/settings/pages
2. Em "Custom domain", verifique se `queerrights.codigonaobinario.org` está listado
3. Se não estiver, adicione manualmente e salve

### 3. Aguardar Propagação

- DNS pode levar de **5 minutos a 48 horas** para propagar completamente
- O GitHub pode levar até **24 horas** para gerar o certificado SSL

### 4. Forçar Verificação

Após configurar o DNS:

1. No GitHub Pages Settings, **remova** o domínio customizado
2. Aguarde 1-2 minutos
3. **Adicione novamente** o domínio: `queerrights.codigonaobinario.org`
4. Salve e aguarde

### 5. Verificar Status

Você pode verificar o status do certificado em:
- https://www.ssllabs.com/ssltest/analyze.html?d=queerrights.codigonaobinario.org

## Checklist

- [ ] DNS CNAME configurado apontando para `travahacker.github.io`
- [ ] DNS propagado (verificar com `dig`)
- [ ] Domínio adicionado nas configurações do GitHub Pages
- [ ] Arquivo CNAME commitado no repositório
- [ ] Aguardado pelo menos 10-15 minutos após configuração
- [ ] Tentado remover e readicionar o domínio no GitHub

## Solução Alternativa Temporária

Se precisar do site funcionando imediatamente, você pode:

1. Remover temporariamente o domínio customizado
2. Usar `travahacker.github.io/QueerRights-web-platform` temporariamente
3. Reconfigurar o domínio customizado depois

## Notas Importantes

- ⚠️ Não use registros A (IPv4) - use apenas CNAME
- ⚠️ Não configure www. junto com o domínio principal (pode causar conflito)
- ✅ O GitHub gera certificados SSL automaticamente via Let's Encrypt
- ✅ O processo pode levar até 24 horas

