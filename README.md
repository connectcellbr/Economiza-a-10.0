# Economiza AI

Aplicativo web de comparação de preços com backend Python, pesquisa multifonte, consultora Economiza AI e busca por foto/OCR.

## Deploy no Render

Este projeto usa Docker para manter o ambiente de execução consistente no Render.

- Runtime: Docker
- Health check: `/api/health`
- **Start Command: deixe vazio** (o `Dockerfile` já inicia `servidor_precos.py`).
- O servidor escuta em `0.0.0.0` e usa automaticamente a variável `PORT` fornecida pelo Render.
- **Não use `python servidor_precos.py` como Start Command se estiver usando Runtime Docker**, porque isso duplica a inicialização do container.
- Se o repositório mantiver esta pasta dentro da raiz, defina `Root Directory` como `economiza_ai_github`.
- O servidor usa automaticamente `PORT` e escuta em `0.0.0.0`.
- `ads.txt` está na raiz para o Google AdSense.

Se configurar manualmente no Render, use **Web Service** conectado ao GitHub. O `render.yaml` já contém a configuração recomendada.

## Pesquisa e loading

A versão atual mantém várias ofertas por loja, usa Mercado Livre + Zoom + mecanismos de busca web em paralelo e também exibe os resultados da pesquisa ampla quando não há preço estruturado. A barra do loading usa a proporção da própria imagem para permanecer alinhada tanto no celular quanto em telas largas.

## GitHub

Envie os arquivos desta pasta para a raiz do repositório. Não envie `__pycache__` nem o ZIP.

## AdSense

O código do AdSense está no painel e o `ads.txt` está na raiz. A exibição efetiva depende da aprovação/configuração do domínio e da disponibilidade de anúncios do Google.
