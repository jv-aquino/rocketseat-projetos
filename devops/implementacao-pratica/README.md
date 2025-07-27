# Plano de Implementação de DevOps
A empresa **Tech** passa por diversos problemas na interface Desenvolvimento-Operações e esse plano aborda uma estratégia para melhorar esse cenário. Para esse plano, será usado majoritariamente a framework de DevOps CALMS, agrupando problemas em diferentes categorias com suas soluções para depois conectar tudo.

*Referência: [link](https://efficient-sloth-d85.notion.site/Desafio-Implementa-o-de-Pr-ticas-DevOps-em-um-Ambiente-Empresarial-Fict-cio-bd3b6b458a5b470d8902f54fdb801cb8)*

### Cultura e Compartilhamento de Conhecimento 
**Problemática**

Atualmente na Tech têm-se a dependência forte uma pessoa herói para manter o sistema de gestão de vendas legado no time de desenvolvimento, já que apenas ela tem o conhecimento da linguagem usada, Delphi. Além disso temos também uma fraca interface entre desenvolvimento e operações / deploy.

**Solução Proposta**

O desenvolvedor Delphi encarregado do sistema legado deve ser aliviado de suas tarefas de desenvolvimento e focar em criar uma documentação adequada da aplicação usando algum software como o Notion ou Obsidian. Ele também no compartilhamento de conhecimento via calls com algum(ns) outro(s) desenvolvedor(es), talvez júnior, para que esse desenvolvedor ou desenvolvedores se tornem capazes de continuar mantendo o software. Se necessário, eventualmente pode-se usar a documentação legada juntamente com os novos desenvolvedores encarregados para fazer o upgrade do sistema para sistemas mais atuais.

Em relação à interface operações-desenvolvimento, é necessário uma melhor comunicação por meio da aplicação das três maneiras. Um dos princípios que se encaixam aqui é o de Ampliar o feedback, que pode ser feito primeiramente com reuniões de entrega integradas entre ambas equipes e metas conjuntas. Além disso podemos utilizar serviços conjuntos como de monitoramento/logs para ampliar a visibilidade dessa ponte dev/prod.

Sugestões aqui seriam softwares open-source como o [Sentry](https://sentry.io/welcome/) ou alguma stack como [Grafana-Loki](https://grafana.com/oss/loki/). É bom lembrar que isso também ataca a questão de Measurements, que será abordado posteriormente.

### Automação e Aceleração de Fluxo
**Problemática**

A empresa tem um tempo médio entre a entrega do código e o deploy de 2 dias atualmente, sendo que há um chance de falha de 20%, com também 8 horas em média de resolução de incidentes. E pior: tudo isso feito manualmente, incluindo os testes em produção.

**Solução Proposta**

Deve-se automatizar os processos tanto de deploy quanto de testes atuais e melhorar essa fase de entrega do código, tanto na parte de reuniões ou ritos de entrega quanto na questão de softwares para actions.

Na questão de automação, podemos usar o [Github Actions](https://github.com/features/actions) ou [Jenkins](https://www.jenkins.io/) para fazer migrações, build e outros scripts de produção automaticamente na máquina que roda os produtos em questão. Antes disso porém, para evitar problemas na produção, também podemos, com definições integradas de Dev e Ops, rodar testes de integração com [Vitest](https://vitest.dev/) (ou similares) e E2E se necessário.

Uma outra sugestão seria rodar scripts de lint pre-commit/pre-push ([Husky](https://typicode.github.io/husky/)) juntamente com uma implementação gradual de linguagens tipadas (TS no lugar de JS) para garantir qualidade de código e menos erros inesperados.

Outras inovações podem também ser implementadas seguindo os ritos apresentados na etapa abaixo, como o uso de IA para revisar PRs, etc.

### Agilidade / Experimentar
Com os pontos abordados acima que devem liberar bastante tempo, também é necessário dar mais liberdade para as equipe tanto de Dev quanto de Ops experimentarem features novas ou jeitos novos de executar. Pode-se reservar tempos livres ou reuniões apenas para discutir possíveis melhorias no sistema (features novas, refactors) ou na maneira que se constrói ele (melhorias de deploy, mudanças de lib, etc.).

Também, se ainda é utilizado, deve-se implementar ritos ágeis por exemplo Scrum ou ter uma tabela Kanban para ampliar a inovação e agilidade.

### Métricas
Por fim, é preciso definir métricas de sucesso para sempre poder garantir a saúde dos produtos e do time.

Para métricas interpessoais, é possível rodar pesquisas de satisfação obrigatórias e anônimas nas equipes para entender como está a produtividade geral, intenções de sair da empresa e a saúde dos times. Assim pode-se direcionar mais recursos ou atenção à certa equipe e planejar mais contratações.

Já os projetos/produtos podem-se utilizar de diferentes tipos de métricas. No Operacional, podemos usar métricas de testes, quantidade de error logs e sistemas para visualizar todos esses dados. Na parte de Desenvolvimento podemos usar scripts para coverage de testes, métricas de perfomance como Lighthouse (do devtools) e talvez uma pré-revisão de código usando IA armazenando dados das reviews.