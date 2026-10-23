# Grana no Controle

Aplicativo web pessoal de orçamento, em português, com tema escuro verde/preto.

## Recursos
- PIN local de 4 a 6 dígitos
- Renda-base inicial de R$ 800
- Categorias e limites editáveis
- Registro, edição e exclusão de entradas e despesas
- Histórico de movimentações
- Metas de economia
- Backup e restauração JSON
- Armazenamento local no navegador
- PWA com service worker para funcionamento offline após a primeira visita

## Como testar
Abra `index.html` num navegador para testar a interface. A experiência de instalação PWA e o funcionamento offline confiável exigem hospedagem em HTTPS ou um servidor local (service workers não funcionam em `file://`).

## Hospedar gratuitamente
Publique os quatro arquivos (`index.html`, `manifest.json`, `sw.js`, `icon.svg`) em um host estático com HTTPS, como GitHub Pages ou Cloudflare Pages. Depois:
1. Abra a URL no Chrome/Android.
2. Espere carregar uma vez com internet.
3. Menu do navegador → “Instalar app” ou “Adicionar à tela inicial”.
4. Crie seu PIN e configure seus limites.

## Privacidade e segurança
Os dados financeiros ficam no `localStorage` desse navegador e não são enviados por este código a um servidor. O PIN cria uma barreira de acesso, mas **não criptografa os dados armazenados**. Quem tiver acesso técnico ao perfil do navegador pode potencialmente ler os dados. Use bloqueio de tela do aparelho e não compartilhe backups JSON. Não há recuperação de PIN: se esquecer, pode ser necessário apagar os dados locais.

## Observações
- O saldo inicial é calculado como renda-base + entradas registradas - despesas registradas.
- A distribuição padrão soma R$ 800: guardar R$ 160, contas R$ 200, alimentação/transporte R$ 120, lazer R$ 100, compras pessoais R$ 80, presentes/assinaturas R$ 40 e reserva R$ 100.
- A categoria “Guardar” é contabilizada como despesa do orçamento, pois representa dinheiro separado do saldo de uso livre.
- Dados do navegador podem ser apagados pelo sistema. Exporte backups regularmente.
