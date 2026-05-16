# Prioridade 1 - Confiabilidade do app

Objetivo: deixar login, cadastro de cliente, plano, perfil e sincronizacao confiaveis antes de divulgar o aplicativo.

## Resultado esperado

Ao final desta prioridade, o app precisa passar nestes testes:

- administrador consegue criar acesso comum;
- administrador consegue criar perfil teste;
- cliente entra com o nome correto;
- cliente ve o plano correto: Mensal, Semestral ou Anual;
- transacao salva continua aparecendo depois de fechar e abrir o app;
- app mostra status claro de salvamento/sincronizacao;
- erros do admin aparecem com mensagem entendivel.

## Etapa concluida: status visual de sincronizacao

O app agora informa melhor o ciclo de salvamento:

- `Salvo no aparelho. Enviando para a nuvem...`
- `Salvando na nuvem...`
- `Salvo na nuvem.`
- `Erro ao salvar na nuvem.`

Tambem mostra um detalhe com horario de confirmacao ou mensagem de erro.

## Etapa 1: Diagnostico do Supabase

Rode o arquivo:

```text
supabase_diagnostico_confiabilidade.sql
```

Ele nao altera dados. Apenas confere se as tabelas, colunas, extensoes e funcoes principais existem.

## Etapa 2: Aplicar SQL unico de confiabilidade

Depois do diagnostico, rode:

```text
supabase_producao_confiabilidade.sql
```

Esse arquivo consolida tabelas, colunas, indices, RLS, funcoes do painel administrador, primeiro acesso, plano e sincronizacao de perfil.

## Etapa 3: Teste controlado

Use este roteiro:

1. Entrar como administrador.
2. Criar um acesso comum com nome real e plano Mensal.
3. Fazer logout.
4. Entrar com esse cliente.
5. Conferir nome e plano em Configuracoes.
6. Criar uma transacao de teste.
7. Fechar totalmente o app.
8. Abrir novamente e conferir se a transacao permaneceu.
9. Voltar ao admin e criar um perfil teste.
10. Entrar no perfil teste.

## Etapa 4: Criterio para avancar

So avancamos para a Prioridade 2 quando estes pontos estiverem aprovados:

- 3 acessos comuns criados sem erro;
- 2 perfis teste criados sem erro;
- 5 transacoes salvas e mantidas apos reabrir o app;
- plano exibido corretamente para cliente mensal, semestral e anual;
- nenhum erro ambiguo no painel admin.
- status de sincronizacao muda corretamente ao criar/editar/excluir transacoes.
- ao sair de admin e entrar como cliente, nome/e-mail/plano do cliente carregam sem mostrar dados do admin.

## Proxima melhoria desta prioridade

Depois que o SQL unico passar, a proxima melhoria sera revisar o status visual da sincronizacao no app:

- mostrar "Salvando..." imediatamente apos uma acao;
- mostrar "Salvo na nuvem" quando confirmar;
- mostrar "Erro ao salvar" quando o Supabase falhar;
- impedir que dados antigos sobrescrevam dados novos.
