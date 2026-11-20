# Origem desta skill

Cópia da skill `security-audit` da Cloudflare, distribuída sob licença MIT (ver `LICENSE`).

- Repositório: https://github.com/cloudflare/security-audit-skill
- Caminho no upstream: `skills/security-audit/`
- Commit copiado: `c1c8a8c1471069fb0e188eeaff69b8e8db6564a8` (14/09/2026)
- Copiada em: 19/11/2026

## O que difere do upstream

Os arquivos de `skills/security-audit/` foram copiados sem alteração, com duas exceções: `validate-findings.test.cjs` e `validate-coverage-ledger.test.cjs` ficaram de fora, porque testam os validadores do próprio upstream e a skill não os usa. `LICENSE` veio da raiz do repositório e este arquivo foi acrescentado.

## Como usar

No Claude Code, dentro do repositório, peça algo como "faça uma auditoria de segurança deste repositório" (auditoria completa, seis fases, com subagentes) ou faça uma pergunta pontual de segurança (modo de orientação, sem gerar arquivos). Na auditoria completa, os artefatos vão por padrão para `~/security-audit-skill/<repo>/run-<N>`, fora do repositório. A skill exige Node.js para os validadores e não executa código do alvo sem sandbox de sistema operacional.

## Como atualizar

```bash
git clone --depth 1 https://github.com/cloudflare/security-audit-skill /tmp/cf-skill
rsync -a --delete --exclude '*.test.cjs' --exclude UPSTREAM.md --exclude LICENSE \
  /tmp/cf-skill/skills/security-audit/ .claude/skills/security-audit/
cp /tmp/cf-skill/LICENSE .claude/skills/security-audit/LICENSE
```

Leia o diff antes de commitar e atualize o commit registrado acima.
