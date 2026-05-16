# Checklist de lançamento

Este checklist organiza o que falta para transformar o Controle Financeiro em um produto vendável em plataformas como Hotmart, Kiwify, Eduzz ou Monetizze.

## 1. Produto

- Definir promessa principal: controle financeiro simples, com painel, contas a pagar/receber, metas, calendário e relatórios.
- Definir público: pessoa física, autônomos, MEI, famílias ou pequenos negócios. Evite vender para todos ao mesmo tempo.
- Criar onboarding inicial com 3 passos: renda principal, contas/carteiras e categorias mais usadas.
- Criar dados de exemplo para conta demo.
- Revisar todos os textos do app com acentos e tom profissional.
- Substituir `prompt()` e `confirm()` por modais do próprio aplicativo.
- Criar uma tela "Ajuda" com dúvidas comuns.

## 2. Segurança e acesso

- Rodar `supabase_melhoria_senha_temporaria_hash.sql` no Supabase para parar de armazenar senha temporária em texto puro.
- Ativar confirmação de e-mail no Supabase ou definir um fluxo claro de primeiro acesso.
- Criar política de recuperação de senha para usuários pagantes.
- Validar Row Level Security em todas as tabelas.
- Remover exposição de senhas antigas no painel administrativo.
- Criar rotina de backup antes de qualquer alteração SQL.

## 3. PWA e hospedagem

- Publicar em domínio próprio com HTTPS.
- Testar instalação no Android, iOS e desktop.
- Validar `manifest.json`, ícone, nome do app e tela inicial.
- Criar screenshots reais para o manifest.
- Remover dependências por CDN em uma versão final com build local.
- Testar funcionamento offline e mensagens de falha de conexão.

## 4. Comercial

- Criar página de vendas com: promessa, público, prints reais, benefícios, perguntas frequentes e garantia.
- Criar vídeo curto mostrando o fluxo: login, nova transação, controle de pagamentos, metas e relatórios.
- Definir oferta: pagamento único, assinatura mensal ou acesso anual.
- Criar termos de uso e política de privacidade.
- Preparar e-mail de boas-vindas com link de acesso, suporte e instruções de primeiro uso.
- Criar canal de suporte: WhatsApp, e-mail ou formulário.

## 5. Testes antes da venda

- Criar usuário comum.
- Criar usuário teste de 30 minutos.
- Bloquear usuário e confirmar que perde acesso.
- Renovar validade e confirmar reativação.
- Criar, editar e apagar transação.
- Criar transação recorrente e excluir apenas uma ocorrência.
- Importar e exportar backup.
- Trocar senha no primeiro acesso.
- Testar em celular pequeno, celular grande e desktop.
- Testar com internet lenta e sem internet.

## 6. Próximas melhorias de produto

- Dashboard com recomendação objetiva: "valor livre", "risco do mês" e "próximas contas".
- Relatórios comparando mês atual com mês anterior.
- Exportação PDF/CSV.
- Gráficos reais para categorias e evolução mensal.
- Lembretes de contas a vencer.
- Tabelas separadas no Supabase para transações, metas, contas e orçamentos.
- Versão com build profissional usando Vite + componentes.
