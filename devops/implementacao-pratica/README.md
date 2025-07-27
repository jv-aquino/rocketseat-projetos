# Plano de Implementação de DevOps
A empresa **Tech** passa por diversos problemas na interface Desenvolvimento-Operações e esse plano aborda uma estratégia para melhorar esse cenário. Para esse plano, será usado majoritariamente a framework de DevOps CALMS, agrupando problemas em diferentes categorias com suas soluções para depois conectar tudo.

### Cultura e Compartilhamento de Conhecimento 
Problemática

Atualmente na Tech têm-se a dependência forte uma pessoa herói para manter o sistema de gestão de vendas legado no time de desenvolvimento, já que apenas ela tem o conhecimento da linguagem usada, Delphi. Além disso temos também uma fraca interface entre desenvolvimento e operações / deploy.

Solução Proposta

O desenvolvedor Delphi encarregado do sistema legado deve ser aliviado de suas tarefas de desenvolvimento e focar em criar uma documentação adequada da aplicação usando algum software como o Notion ou Obsidian. Ele também no compartilhamento de conhecimento via calls com algum(ns) outro(s) desenvolvedor(es), talvez júnior, para que esse desenvolvedor ou desenvolvedores se tornem capazes de continuar mantendo o software. Se necessário, eventualmente pode-se usar a documentação legada juntamente com os novos desenvolvedores encarregados para fazer o upgrade do sistema para sistemas mais atuais.

Em relação à interface operações-desenvolvimento, é necessário uma melhor comunicação por meio da aplicação das três maneiras. Um dos princípios que se encaixam aqui é o de Ampliar o feedback, que pode ser feito primeiramente com reuniões de entrega integradas entre ambas equipes e metas conjuntas. Além disso podemos utilizar serviços conjuntos como de monitoramento/logs para ampliar a visibilidade dessa ponte dev/prod.

Sugestões aqui seriam softwares como o Sentry ou algo open-source como Grafana Loki. É bom lembrar que isso também ataca a questão de Measurements, que será abordado posteriormente.