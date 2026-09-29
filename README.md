# Aula 03 — Autorização & Senhas — Laboratório
IDOR, autorização por objeto, RBAC, MD5→BCrypt e rate limiting. Parte do **Curso CASE Java (Certified Application Security Engineer)**.

> ⚠️ Aplicação **propositalmente vulnerável**, para fins didáticos. Não use em produção.

## Como rodar (sem Docker, banco H2 em memória)
```bash
git clone https://github.com/tiagocanatelliretechers/curso-case-java-aula-3-autorizacao.git
cd curso-case-java-aula-3-autorizacao
./scripts/start.sh --no-docker        # Windows: .\scripts\start.ps1 -NoDocker
```
Acesse <http://localhost:8080> — contas: `admin@portal.com/admin123`, `joao@acme.com/senha123`.

## Branches
- **main** — *baseline*: código vulnerável, ponto de partida do laboratório.
- **hardened** — solução de referência: `git checkout hardened` para comparar.

## Materiais (`materiais/`)
- **lab.md** — guia do aluno (autoguiado: o que observar, o que significa, ponto de entendimento, troubleshooting).
- **roteiro-demonstracao.md** — pré-lab pronto para o **instrutor demonstrar** (exploit → hardened → provar → mostrar código).
- **lab-aula-3.pptx** — deck do laboratório.
- **conteudo-…pptx** — slides de conteúdo (teoria).
- **GUIA-DO-INSTRUTOR.md** — a dinâmica de aula e o roteiro.

## Fluxo do laboratório
1. Leia `materiais/lab.md`.
2. Rode e explore a falha (branch **main**).
3. Corrija seguindo o lab — ou compare com a branch **hardened**.
