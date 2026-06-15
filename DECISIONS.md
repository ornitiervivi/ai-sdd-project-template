# DECISIONS.md

Registre decisões arquiteturais e técnicas relevantes.

## Template inicial

- Data: 2026-06-15
- Decisão: criar estrutura genérica para projetos SDD com harness de IA.
- Motivo: padronizar planejamento, implementação, revisão, validação e aprendizado.
- Consequências: projetos derivados devem preencher documentação antes de implementar produto real.

## Regras Java/Spring e idioma padrão

- Data: 2026-06-15
- Decisão: reforçar que projetos Java/Spring derivados devem aplicar Clean Code, Clean Architecture, SOLID, design patterns apropriados, bibliotecas que reduzam boilerplate e 100% de cobertura de linhas e branches em classes de regras de negócio.
- Decisão: definir inglês como idioma padrão para código, contratos técnicos e documentação técnica do projeto derivado, evitando mistura de idiomas.
- Motivo: aumentar consistência, legibilidade, manutenibilidade e qualidade das regras de negócio.
- Consequências: exceções de idioma devem ser explícitas e isoladas, e classes de regra de negócio exigem validação de cobertura mais rigorosa.


## Orquestração por papéis no harness

- Data: 2026-06-15
- Decisão: adicionar `AGENT_ROLES.md` e tornar obrigatório o uso de papéis especializados simulados ou reais conforme o escopo da tarefa.
- Motivo: aumentar rastreabilidade, reduzir riscos por especialidade e padronizar análise, arquitetura, implementação, segurança, validação, revisão e documentação viva sem transformar o template em produto real.
- Consequências: agentes devem selecionar papéis antes de tarefas não triviais, consultar skills compatíveis e registrar dúvidas, riscos, validações e documentação conforme cada papel.
