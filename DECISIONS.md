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
