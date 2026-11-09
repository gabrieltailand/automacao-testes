# Tipos de testes

* Testes de unidade
* Testes de integração ou de serviço
* testes E2E (End-to-end, ponta a ponta) (Interface)
    * Foco: testa fluxos inteiros de interação do usuário (Ex: desde visitar a página inicial até fazer um login)
    * Tempo de execução alto
    * Custo alto
    * Podem ser realizados por profissionais QA ou os desenvolvedores
    * Podem ser manuais ou automatizados
    * Não se preocupam com a tecnologia que está sendo usada no projeto
    * Começar testando os pontos mais críticos da aplicação

# Usando CLI e extensão

Sabia que muitas das coisas que fizemos pela interface visual do Playwright (como executar apenas um único teste, um arquivo de testes, escolher em quais navegadores testar) também podem ser feitas pela linha de comando?

* Você já sabe como rodar todos os testes do projeto:

```script
npx playwright test
# ou usando nosso script "e2e":
npm run e2e
```

* Para rodar os testes apenas em um tipo de navegador, use a flag `--project`:

```script
npx playwright test --project=chromium
# ou usando nosso script "e2e":
npm run e2e -- --project=chromium
# o hífen duplo "--" é necessário para adicionar flags ao script
```

* Para rodar os testes de um único arquivo, passe o nome dele:

```script
npm run e2e example.spec.ts -- --project=chromium
```

* Para rodar os arquivos de testes que contêm `example` ou `PaginaInicial` no nome (irá rodar ambos `example.spec.ts` e `visitarPaginaInicial.spec.ts)`, passe essas palavras para o comando:

```script
npm run e2e example PaginaInicial -- --project=chromium
```

* Para rodar testes a partir de seus títulos, use a flag `-g`:

```script
npm run e2e -- -g "página inicial" --project=chromium
```

Você pode conferir mais detalhes nas páginas [Running and debugging tests](https://playwright.dev/docs/running-tests) e [Command Line](https://playwright.dev/docs/test-cli) da documentação! Esses comandos podem ser muito úteis caso você deseje integrar seus testes em uma ferramenta de CI (Continuous Integration).

## Extensão do VSCode

Além disso, o Playwright também possui uma [extensão do VSCode](https://playwright.dev/docs/getting-started-vscode) para você rodar os testes diretamente no editor, caso desejar! Não utilizaremos essa extensão no curso, pois focaremos na interface visual do Playwright.

A extensão foi feita pela Microsoft, assim como o próprio VSCode e o Playwright, então todas essas ferramentas se integram de forma muito bacana. :)