## Objetivo

Este repositório contém um app Python simples com o entrypoint `app.py`. O arquivo atual está vazio; estas instruções ajudam um agente de codificação a ser produtivo rapidamente: entender o escopo, onde editar, convenções locais e como validar mudanças.

## Panorama rápido (o que há no repositório)

- `app.py` — ponto de entrada da aplicação (single-file dashboard web app presumido). Atualmente vazio.

Nota: não há `requirements.txt`, `README.md` nem pastas adicionais encontradas. Assuma que este é um micro-projeto Python até novas evidências.

## Prioridades ao editar

- Ao adicionar funcionalidade, edite `app.py` como o ponto de entrada principal. Mantenha a API pública estável: exponha uma função `create_app()` (retornando a app/framework object) e preserve o bloco `if __name__ == '__main__':` para execução direta.
- Coloque código reutilizável em novos módulos (ex: `app/__init__.py`, `app/routes.py`) quando o arquivo crescer — prefira criar uma pasta `app/` para organização.

Exemplo mínimo recomendado em `app.py` (padrão a seguir):

- `def create_app():` — constrói e configura a app.
- `if __name__ == '__main__':` — arranca o servidor em modo desenvolvimento.

## Convenções e padrões locais

- Projeto atual é mínimo; adote convenções comuns, porém documente qualquer escolha não trivial dentro de `README.md` ou na própria função/módulo.
- Configure dependências em `requirements.txt` no nível raiz. Evite instalar globalmente.
- Use variáveis de ambiente para configuração (ex: `PORT`, `FLASK_ENV`, `APP_DEBUG`). Procure por `os.environ` ao ler ou modificar configuração.

## Fluxo de desenvolvimento e verificação (PowerShell — Windows)

1. Criar e ativar venv:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

2. Instalar dependências (se existir `requirements.txt`):

```powershell
pip install -r requirements.txt
```

3. Executar localmente:

```powershell
python app.py
```

4. Ao adicionar dependências, adicione/atualize `requirements.txt` e documente o propósito.

## Testes e validação

- Não foram encontrados testes neste repositório. Se criar testes, use a pasta `tests/` e prefira `pytest` como runner.
- Minimal: crie um teste que importe `create_app()` e execute client requests para rotas mais importantes.

## Mensagens de commit e PRs

- Prefira commits pequenos e focados. Descreva a motivação e o comportamento introduzido no título/descrição do PR.

## Integrações e dependências externas

- Não há integrações detectadas. Se adicionar integrações (DB, APIs), documente credenciais e variáveis necessárias em `README.md` e use variáveis de ambiente para segredos.

## Exemplos de instruções específicas para o agente

- "Se for adicionar uma rota web, implemente `create_app()` em `app.py` e escreva um teste em `tests/test_routes.py` que verifica 200 OK para `/`".
- "Ao adicionar dependência, atualize `requirements.txt` e inclua instruções curtas no `README.md` sobre como rodar localmente".

## Perguntas para o mantenedor (quando em dúvida)

- Qual framework web preferido (Flask, FastAPI, outro)?
- Há um arquivo de dependências preferido (requirements.txt, pyproject.toml)?
- Deseja estrutura multi-módulo (`app/`, `tests/`) desde já ou prefere manter single-file?

---

Se quiser, eu posso: (1) criar um `README.md` com comandos de execução, (2) iniciar uma estrutura `app/` e exemplo `create_app()` em `app.py`, ou (3) adicionar um `requirements.txt` com `flask` exemplo. Diga qual dessas opções prefere.
