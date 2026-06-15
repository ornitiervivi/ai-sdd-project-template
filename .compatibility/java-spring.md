# Compatibilidade — Java/Spring

## Versões

- Java: definir no projeto derivado.
- Spring Boot: definir no projeto derivado.
- Build tool: Maven ou Gradle, a definir.

## Regras obrigatórias

- Não usar `record`.
- Não adicionar comentários no código.
- Não fazer mudanças não solicitadas.
- Preferir classes completas, explícitas e testáveis.
- Manter nulidade segura.
- Evitar listas longas de parâmetros; usar objetos de comando, request ou configuração.
- Preservar compatibilidade binária e de API pública quando aplicável.

## Bibliotecas

Adicionar dependências somente com justificativa registrada em `DECISIONS.md`.
