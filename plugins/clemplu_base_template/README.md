# Plugin Base Clematis (`.clemplu`)

Este diretório é o modelo oficial para criar plugins comunitários no formato **`.clemplu`** para o **Clematis Player v0.7.1+**.

## Estrutura do pacote `.clemplu` (arquivo ZIP renomeado para `.clemplu`)

```text
meu_plugin.clemplu (ZIP)
├── manifest.json       # Metadados obrigatórios e capabilities declarativas
├── icon.svg            # Ícone de capa do plugin (.svg ou .png)
└── data/
    ├── frame.json      # Configuração declarativa da moldura
    └── frame.svg       # Arte SVG ou PNG com centro transparente (256x256+)
```

## Campos obrigatórios do `manifest.json`
- `id`: identificador único em minúsculas (`a-z`, `0-9`, `.`, `_`, `-`).
- `name`: nome exibido na aba de Plugins.
- `version`: versão semântica (ex.: `1.0.0`).
- `author`: nome do criador.
- `description`: descrição curta do recurso.
- `minClematisVersion`: versão mínima compatível (ex.: `0.7.1`).
- `icon`: caminho relativo do ícone na raiz (`icon.svg` ou `icon.png`).
- `capabilities`: lista de capacidades declarativas suportadas (ex.: `["profile_frame"]`).

## Regras de Segurança
- Plugins `.clemplu` são **estritamente declarativos**: nenhum script ou binário executável (`.js`, `.py`, `.exe`, `.dll`, `.sh`, `.bat`, `.apk`, `.so`) é aceito ou executado.
- Apenas extensões de dados/mídia seguras (`.json`, `.svg`, `.png`, `.jpg`, `.webp`, `.txt`, `.md`) até 15 MB são aceitas.
- O Clematis valida integridade e bloqueia travessia de diretórios (`Zip-Slip`) antes de promover a instalação.

## Como empacotar seu `.clemplu`
Compacte o conteúdo interno da pasta (com `manifest.json` na raiz do ZIP) e renomeie a extensão de `.zip` para `.clemplu`. Depois abra **Clematis > Plugins & Extensões > Importar Plugin (.clemplu)**.
