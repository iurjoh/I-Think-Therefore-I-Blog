# I Think Therefore I Blog

**Português (Brasil)** | [English](README.md)

Projeto de estudo de blog Django baseado no template Code Institute. O código revisado inclui lista de publicações, detalhe, comentários aprovados e curtidas.

**Documentação revisada:** 01/10/2026. O endereço das configurações, https://iurjoh-blog.herokuapp.com/, respondeu HTTP 404 com a página Heroku "No such app" nessa data. Nenhum deploy ativo ali foi confirmado.

## Ideia e registro de desenvolvimento

O código organiza um blog com modelos, views e templates HTML Django. O README anterior era o template genérico Gitpod, não um registro de planejamento. Não inventamos pesquisa de usuários, escolhas de design ou histórico de testes aprovados; as alterações estão no git.

## Arquitetura

```text
Navegador -> URLs do blog -> views Django -> modelos/banco
                                        -> templates HTML
                                        -> comentários e curtidas
```

`PostList` seleciona publicações em ordem da mais nova, com seis itens por página. `PostDetail` mostra comentários aprovados e processa o formulário. `PostLike` alterna a relação de curtida. Configurações ficam em `codestar/`, com `DATABASE_URL` e `SECRET_KEY` do ambiente.

`requirements.txt` registra Django 3.2.16, Allauth 0.52, Cloudinary, Crispy Forms, Social Share, Summernote, Gunicorn e psycopg2. São versões históricas, não recomendação para produção nova.

## Configuração local

Use ambiente isolado e dados fictícios:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Configure `SECRET_KEY` e `DATABASE_URL` locais conforme `codestar/settings.py`; o exemplo SQLite está comentado. Não use banco de produção nem publique segredos.

```bash
python3 manage.py migrate
python3 manage.py runserver
```

Os passos não foram executados nesta atualização. Reveja compatibilidade das dependências antes de reutilizar.

## Design, testes e segurança

A revisão cobriu configurações, views, rotas, dependências e README anterior. Não executou testes, migrações ou revisão visual do app. `DEBUG` está ligado no código, e as views de comentários/curtidas revisadas não têm bloqueio explícito de login. Teste acesso no servidor, validação, CSRF, filtro de aprovação e dependências antes de publicar. Há banco versionado no repositório; reveja seu conteúdo em privado antes de compartilhar ou republicar, sem presumir dados fictícios.

Nenhum snapshot novo foi embutido. Screenshots futuros devem ser datados, usar conteúdo fictício e ficar em `docs/assets/`.

## Créditos e licença

Template e curso Code Institute, além de dependências de terceiros. Nenhum `LICENSE` foi encontrado na raiz. Preserve seus termos; não aplicamos MIT a código de terceiros nem usamos notas do template como histórico do autor.
