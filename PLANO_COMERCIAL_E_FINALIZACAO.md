# Plano comercial e finalização do Controle Financeiro

Este documento é o guia de execução para levar o aplicativo até o ponto de venda em plataformas como Hotmart, Kiwify, Eduzz ou Monetizze.

## 1. Posicionamento recomendado

Minha sugestão é vender o aplicativo como um controle financeiro pessoal simples, visual e guiado para quem quer organizar contas sem planilhas complexas.

### Promessa principal

Organize receitas, despesas, contas a pagar, contas a receber, metas e relatórios em um painel simples que funciona no celular.

### Público ideal inicial

- Pessoas físicas que querem controlar o mês.
- Autônomos e MEIs que misturam entradas, despesas e recebíveis.
- Famílias que querem prever contas e evitar atraso.

Evite posicionar inicialmente como sistema contábil, ERP ou gestão empresarial completa. Isso aumenta expectativa, suporte e risco.

## 2. Estrutura de planos

Eu recomendo três planos simples:

| Plano | Preço sugerido | Objetivo |
| --- | ---: | --- |
| Mensal | R$ 19,90 a R$ 29,90/mês | Entrada acessível e teste real |
| Semestral | R$ 97,00 a R$ 127,00/6 meses | Melhor custo-benefício |
| Anual | R$ 167,00 a R$ 247,00/ano | Oferta principal |

### Minha opinião sobre preço

Começaria com:

- Mensal: R$ 24,90
- Semestral: R$ 119,00
- Anual: R$ 197,00

O anual deve parecer claramente melhor. O mensal é útil para quem tem medo de assinar, mas a página de vendas deve destacar o anual.

## 3. O que cada plano entrega

Como o app ainda é um produto único, a diferença entre planos deve ser principalmente tempo de acesso, não recurso. Isso simplifica suporte e evita confusão.

### Todos os planos

- Painel financeiro.
- Receitas e despesas.
- Contas a pagar e a receber.
- Calendário financeiro.
- Metas.
- Relatórios.
- Backup/importação.
- Acesso pelo celular como PWA.
- Suporte básico.

### Bônus para semestral e anual

- Modelo de rotina financeira semanal.
- Guia rápido em PDF.
- Acesso prioritário a melhorias.

### Bônus somente anual

- Suporte prioritário.
- Renovação com desconto.
- Acesso antecipado a novas telas.

## 4. Estrutura de acesso no app

O app já tem uma base boa para venda com validade de acesso:

- Admin cria acesso.
- Define validade.
- Define plano pelo tempo de acesso.
- Bloqueia ou renova o cliente.

### Ajuste recomendado no painel admin

Adicionar campo `Plano` com opções:

- Mensal
- Semestral
- Anual
- Teste

Também recomendo exibir:

- Data de início.
- Data de expiração.
- Status de pagamento.
- Origem da compra: Hotmart, Kiwify, manual.

## 5. Fluxo de venda manual inicial

Para começar sem automação complexa:

1. Cliente compra na Hotmart/Kiwify.
2. Plataforma envia e-mail de confirmação.
3. Você recebe a notificação.
4. Você cria o acesso no painel admin.
5. Cliente recebe e-mail/WhatsApp com link, login e senha temporária.
6. Cliente troca a senha no primeiro acesso.

Este fluxo é suficiente para vender as primeiras unidades com segurança operacional.

## 6. Fluxo automatizado futuro

Depois das primeiras vendas, dá para automatizar:

1. Hotmart/Kiwify envia webhook de compra aprovada.
2. Uma função no servidor valida a compra.
3. O sistema cria ou renova o acesso automaticamente.
4. Cliente recebe e-mail automático.
5. Cancelamento ou reembolso bloqueia o acesso.

Não recomendo começar pela automação total antes de validar a venda.

## 7. Prioridades de melhoria do aplicativo

### Fase 1: aparência profissional

- Usar logos oficiais.
- Corrigir textos e acentos.
- Remover `prompt()` e `confirm()`.
- Criar modais profissionais.
- Criar tela de ajuda.
- Melhorar mensagens de erro.

### Fase 2: venda e suporte

- Criar página "Ajuda".
- Criar tela "Minha assinatura".
- Mostrar plano atual e validade.
- Criar instruções de primeiro acesso.
- Criar política de privacidade e termos de uso.

### Fase 3: segurança e estabilidade

- Aplicar hash para senha temporária.
- Revisar RLS no Supabase.
- Testar usuário comum, admin e perfil teste.
- Melhorar backup.
- Remover dependências por CDN em versão final.

### Fase 4: produto premium

- Comparativo mês atual vs mês anterior.
- Gráfico de evolução mensal.
- Exportação PDF/CSV.
- Lembretes de contas a vencer.
- Onboarding inicial.
- Dados demo para apresentação.

## 8. Conteúdo para página de vendas

### Headline sugerida

Controle Financeiro simples para organizar seu mês pelo celular

### Subtítulo

Registre receitas, despesas, contas a pagar, contas a receber, metas e acompanhe sua saúde financeira em um painel direto ao ponto.

### Benefícios

- Veja quanto entrou, saiu e ainda está pendente.
- Controle contas a pagar e a receber.
- Acompanhe o mês por calendário.
- Crie metas financeiras.
- Use no celular como aplicativo instalado.
- Tenha acesso seguro com login e senha.

### Garantia

Garantia de 7 dias, conforme regra da plataforma de venda.

## 9. Próximos passos de execução

1. Finalizar identidade visual com logos oficiais.
2. Criar modais profissionais para confirmações.
3. Criar tela "Minha assinatura".
4. Adicionar campo de plano no banco e no painel admin.
5. Criar tela de ajuda/onboarding.
6. Aplicar SQL de senha temporária com hash.
7. Testar fluxo completo de compra manual.
8. Preparar página de vendas.
