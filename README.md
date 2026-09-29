# Aula 02 — SQLi · Validação · Upload  ·  (COM)
Branch de apoio no repositório da Aula 3, para **explicar a Aula 2**: a mesma aplicação COM os tratamentos de segurança.

> ⚠️ App didático. Esta branch é **COM tratamentos** — ver abaixo.

## O que a Aula 2 trata (tratamentos)
- **SQL Injection** em `/produtos/buscar` → `ProdutoService` (query parametrizada).
- **Validação de entrada** (CNPJ) → `dto/CNPJ.java`, `CnpjValidator`, `CadastroClienteForm`.
- **Upload inseguro** → `UploadService` (tipo/tamanho/isolamento).

Nesta branch os tratamentos **já foram aplicados** (query parametrizada, validação, upload seguro). Compare com `aula-2-sem-tratamentos`.

## Rodar
```bash
./scripts/start.sh --no-docker        # Windows: .\scripts\start.ps1 -NoDocker
```
Acesse <http://localhost:8080>. Contas: `admin@portal.com/admin123`, `joao@acme.com/senha123`.

## Demonstrar o SQL Injection (com o app no ar)
```bash
curl -s -G "http://localhost:8080/produtos/buscar" \
  --data-urlencode "termo=zzz' UNION SELECT id,email,senha,0,0 FROM usuario --"
```
- **sem tratamentos:** vazam e-mails/hashes no lugar dos produtos.
- **com tratamentos:** a query é parametrizada — nada vaza.

## Branches deste repositório
- `main` — Aula 3 baseline (== Aula 2 **com** tratamentos).
- `hardened` — Aula 3 solução.
- `aula-2-sem-tratamentos` — Aula 2 **sem** os tratamentos (vulnerável).
- `aula-2-com-tratamentos` — Aula 2 **com** os tratamentos (corrigido).

Materiais da Aula 2 em `materiais/` (lab, slides, conteúdo).
