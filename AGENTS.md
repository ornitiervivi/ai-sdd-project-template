# AGENTS.md — ai-sdd-app-template

Este repositório é um template genérico para aplicações criadas com **Spec-Driven Development (SDD)** e **harness de IA**. Não implemente um produto real aqui: use este repositório como base para novos projetos.

## Regra central obrigatória

Antes de qualquer implementação, o agente deve ler e considerar os arquivos relevantes do SDD/harness:

1. `PROJECT_CONTEXT.md`
2. `SPEC.md`
3. `ARCHITECTURE.md`
4. `DECISIONS.md`
5. `TASKS.md`
6. `PLAN.md`
7. `AI_HARNESS.md`
8. `SKILLS.md`
9. `VALIDATION.md`
10. `CODE_REVIEW.md`
11. Arquivos aplicáveis em `.compatibility/`
12. Skills aplicáveis em `.skills/*/SKILL.md`

Se algum arquivo estiver vazio, incompleto ou conflitante, trate isso como informação relevante e registre a lacuna no plano ou faça perguntas bloqueantes.

## Fluxo de trabalho obrigatório

1. **Entender antes de agir**
   - Leia a especificação e o contexto antes de propor código.
   - Identifique escopo, restrições, riscos, dependências e critérios de aceite.

2. **Planejar antes de codar**
   - Atualize ou consulte `PLAN.md` e `TASKS.md` antes de implementar.
   - Divida alterações em passos pequenos, verificáveis e reversíveis.

3. **Perguntar dúvidas bloqueantes**
   - Pergunte antes de implementar quando houver ambiguidade que possa alterar arquitetura, contrato, modelo de dados, segurança, UX, custo ou compatibilidade.
   - Não invente requisitos de negócio.

4. **Alterar somente o necessário**
   - Faça a menor mudança que resolva a tarefa.
   - Não refatore código não relacionado.
   - Não altere formatação, dependências, APIs públicas ou arquitetura sem necessidade explícita.

5. **Manter documentação viva**
   - Atualize documentação junto com a mudança.
   - Atualize `SPEC.md` quando requisitos mudarem.
   - Atualize `ARCHITECTURE.md` quando estrutura, limites ou integrações mudarem.
   - Atualize `DECISIONS.md` quando houver decisão técnica relevante.
   - Atualize `TASKS.md` e `PLAN.md` quando tarefas forem criadas, concluídas ou replanejadas.

6. **Registrar bugs e aprendizados**
   - Registre defeitos relevantes em `BUGS.md`.
   - Registre causa raiz, prevenção e lições em `LESSONS_LEARNED.md`.

7. **Validar sempre que possível**
   - Execute build, testes, lint, typecheck, migrações ou validações aplicáveis.
   - Se não puder validar por limitação de ambiente, registre claramente a limitação.

8. **Revisar antes de entregar**
   - Faça revisão técnica contra `CODE_REVIEW.md`.
   - Verifique regressões, segurança, compatibilidade, legibilidade, testes e documentação.

## Regras gerais de engenharia

- Prefira arquitetura limpa, baixo acoplamento e alta coesão.
- Aplique SOLID com pragmatismo.
- Use Clean Code: nomes expressivos, funções pequenas, responsabilidades claras e ausência de complexidade acidental.
- Use design patterns apenas quando simplificarem o modelo ou reduzirem acoplamento.
- Proteja invariantes de domínio no local correto.
- Evite duplicação prematura e abstrações especulativas.
- Escreva testes automatizados proporcionais ao risco.
- Preserve compatibilidade de versões conforme `.compatibility/`.
- Prefira contratos explícitos, validação de entrada e tratamento consistente de erros.
- Nunca exponha segredos, tokens ou dados sensíveis.

## Backend

- Separe domínio, aplicação, infraestrutura e interfaces.
- Mantenha controllers/adapters finos.
- Centralize regras de negócio em serviços ou objetos de domínio.
- Valide entradas nas bordas e invariantes no domínio.
- Use transações de forma explícita e mínima.
- Garanta observabilidade básica: logs úteis, métricas e rastreamento quando aplicável.

## Frontend

- Componentes devem ser pequenos, acessíveis e testáveis.
- Separe estado de UI, estado remoto e regras de apresentação.
- Evite lógica de negócio profunda em componentes visuais.
- Preserve acessibilidade, responsividade e performance.
- Não introduza dependências visuais pesadas sem justificativa.

## Banco de dados

- Modele dados a partir dos casos de uso e invariantes.
- Use migrações versionadas e reversíveis quando possível.
- Defina índices por padrões reais de consulta.
- Evite mudanças destrutivas sem plano de migração.
- Documente decisões de consistência, isolamento e retenção.

## Segurança

- Segurança deve ser considerada desde o planejamento.
- Aplique menor privilégio, validação de entrada, encoding de saída e proteção contra abuso.
- Não registre dados sensíveis.
- Trate autenticação, autorização, auditoria e gestão de segredos como requisitos explícitos.
- Consulte `.compatibility/security.md` e `.skills/security/SKILL.md` para tarefas sensíveis.

## DevOps

- Automatize build, testes e entrega de forma reprodutível.
- Use configuração por ambiente sem acoplar segredos ao código.
- Prefira infraestrutura declarativa quando aplicável.
- Preserve compatibilidade com pipelines existentes.
- Documente comandos operacionais em `README.md` ou `VALIDATION.md`.

## Java/Spring

Para projetos Java/Spring derivados deste template:

- **Proibido usar `record`.** Use classes completas.
- **Proibido adicionar comentários no código.** O código deve ser expressivo por nomes, tipos e estrutura.
- **Proibido fazer mudanças não solicitadas.**
- Quando alterar uma classe, entregue a classe completa e consistente.
- Use código expressivo, baixa complexidade ciclomática e métodos coesos.
- Prefira nulidade segura: valide entradas, use tipos adequados e evite `NullPointerException`.
- Prefira objetos de parâmetro ou comandos em vez de listas longas de parâmetros.
- Separe DTOs, entidades, serviços, repositórios e mapeadores.
- Evite lógica de negócio em controllers.
- Use exceções e respostas de erro consistentes.

## Evolução do template

- Este template deve permanecer genérico.
- Não adicione regras específicas de um produto sem marcá-las como exemplo ou placeholder.
- Ao melhorar o template, atualize `TECH_RADAR.md`, `DECISIONS.md` e skills relevantes.
