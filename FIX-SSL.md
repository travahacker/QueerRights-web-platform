# Solução: Site "Não Seguro" - Certificado SSL

## Problema Identificado

O DNS está configurado corretamente, mas o GitHub ainda não gerou o certificado SSL para o domínio customizado. O certificado atual é para `*.github.io`, não para `queerrights.codigonaobinario.org`.

## Solução Passo a Passo

### 1. Verificar Configuração no GitHub Pages

1. Acesse: https://github.com/travahacker/QueerRights-web-platform/settings/pages
2. Em "Custom domain", verifique se `queerrights.codigonaobinario.org` está listado
3. Se não estiver, adicione e salve

### 2. Forçar Verificação do Domínio

Para acelerar o processo de geração do certificado:

1. **Remova** o domínio customizado no GitHub Pages Settings
2. Aguarde **2-3 minutos**
3. **Adicione novamente** o domínio: `queerrights.codigonaobinario.org`
4. **Salve** e aguarde

### 3. Aguardar Geração do Certificado

- ⏱️ O GitHub pode levar de **10 minutos a 24 horas** para gerar o certificado SSL
- 🔄 O processo é automático via Let's Encrypt
- ✅ Você receberá um email quando o certificado estiver pronto (se configurado)

### 4. Verificar Status

Após alguns minutos, verifique:

```bash
# Verificar se o certificado foi gerado
openssl s_client -connect queerrights.codigonaobinario.org:443 -servername queerrights.codigonaobinario.org </dev/null 2>/dev/null | grep "subject="
```

Quando funcionar, deve mostrar algo como:
```
subject=CN=queerrights.codigonaobinario.org
```

### 5. Habilitar HTTPS Enforcement

Após o certificado ser gerado:

1. Volte para GitHub Pages Settings
2. Em "Enforce HTTPS", deve aparecer a opção para habilitar
3. Marque "Enforce HTTPS"
4. Salve

## Solução Temporária

Se precisar do site funcionando imediatamente:

1. Use temporariamente: `http://queerrights.codigonaobinario.org` (sem HTTPS)
2. Ou use: `https://travahacker.github.io/QueerRights-web-platform`

## Checklist

- [ ] DNS CNAME configurado corretamente ✅
- [ ] Domínio adicionado no GitHub Pages Settings
- [ ] Aguardado pelo menos 10-15 minutos
- [ ] Tentado remover e readicionar o domínio
- [ ] Verificado se o certificado foi gerado

## Tempo Estimado

- **Mínimo**: 10-15 minutos
- **Médio**: 1-2 horas
- **Máximo**: 24 horas

## Nota Importante

O GitHub Pages gera certificados SSL automaticamente via Let's Encrypt. O processo é automático, mas pode levar tempo. Não há como acelerar além de garantir que tudo está configurado corretamente.

