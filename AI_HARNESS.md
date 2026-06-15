# AI_HARNESS.md

## Objetivo

Definir como agentes de IA devem operar no projeto.

## Regras do harness

- Ler contexto e especificação antes de editar.
- Manter rastreabilidade entre requisito, decisão, tarefa, código, teste e validação.
- Preferir mudanças pequenas e auditáveis.
- Não inventar requisitos.
- Registrar incertezas, bugs e aprendizados.
- Evitar alterações irrelevantes.

## Orquestração por papéis

O harness exige o uso dos papéis definidos em `AGENT_ROLES.md`. O agente deve selecionar papéis por escopo, simular suas revisões quando subagents reais não existirem e usar os resultados para guiar plano, implementação, validação e documentação.

Papéis obrigatórios por tipo de tarefa:

- Requisitos, escopo ou critérios de aceite: Product Analyst.
- Arquitetura, limites, integrações ou riscos técnicos: Solution Architect.
- Backend: Backend Engineer.
- Interface web, mobile, painel ou UX: Frontend/Mobile Engineer.
- Modelo de dados, migrações, índices ou consistência: Database Engineer.
- Voz, transcrição, parser, IA ou confirmação humana: AI/Voice Engineer.
- Autenticação, autorização, dados sensíveis, abuso ou dependências: Security Reviewer.
- Build, Docker, ambientes, CI/CD ou operação: DevOps Engineer.
- Estratégia de testes, cobertura ou validação: QA/Test Engineer.
- Qualidade, regressões e compatibilidade antes da entrega: Code Reviewer.
- Documentação viva e rastreabilidade SDD: SDD Scribe.

A ordem padrão é entender requisitos, definir arquitetura, implementar com papéis especializados, revisar segurança, validar testes/operação, revisar código e atualizar documentação.

## Checklist mínimo do agente

- Contexto lido.
- Escopo entendido.
- Dúvidas bloqueantes resolvidas.
- Plano definido.
- Papéis especializados selecionados conforme `AGENT_ROLES.md`.
- Compatibilidade consultada.
- Validação executada ou limitação registrada.
- Revisão técnica concluída.
