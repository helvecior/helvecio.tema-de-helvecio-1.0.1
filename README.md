# Tema Mariana for VS Code

![Ícone](images/icon.png)

Extensão que adapta para o VS Code as configurações do tema Mariana do Sublime Text, com equivalências de interface baseadas no Default Dark e ajustes pessoais de pesquisa e seleção. Projeto independente.

## Créditos e situação da licença

Esta é uma adaptação independente, sem afiliação, patrocínio ou endosso da Sublime HQ ou da Microsoft. Sublime Text e Visual Studio Code são citados apenas para identificar a origem e a compatibilidade do projeto.

O esquema Mariana de origem identifica **Sublime HQ Pty Ltd e Dmitri Voronianski** como autores. A base de interface também utiliza configurações do Default Dark do Sublime Text. A conversão para o VS Code e os ajustes pessoais não transferem a autoria dos componentes originais.

**A autorização de redistribuição dos arquivos de origem ainda não foi confirmada.** Este pacote não deve ser apresentado como autorizado para publicação pública ou como inteiramente licenciado sob MIT, Apache ou outra licença aberta. O campo `UNLICENSED` foi mantido enquanto essa verificação está pendente; ele não significa domínio público e não concede direitos sobre os componentes de terceiros.

Veja [os créditos e a origem](CREDITOS.md) e [as pendências de licenciamento](LICENCIAMENTO.md). Nenhuma licença dos arquivos originais foi incluída por suposição.

## Instalação

1. Extraia o ZIP e localize `tema-mariana-for-vs-code-2.0.1.vsix`.
2. No VS Code, abra Extensões, clique em `…` e escolha **Instalar do VSIX…**.
3. Se for solicitado, reinicie o VS Code. Use Ctrl+K, Ctrl+T e selecione **Tema Mariana for VS Code**.

A versão 2.0.1 mantém os identificadores internos da extensão anterior para permitir sua atualização. Esta pasta é uma entrega para instalação; não foi instalada automaticamente.

## Ícones

O ícone ativo é `images/icon.png`, em 128 × 128 pixels. As cinco alternativas estão em `images/opcoes/`. Para trocar, copie a opção desejada sobre `images/icon.png` e gere novamente o instalador. Trocar apenas o arquivo fora do VSIX não altera um instalador já gerado.

## Cores personalizadas

As propriedades abaixo ficam em `colors`, no arquivo `themes/Mariana-Default-Dark.color-theme.json`.

| Propriedade | Cor | Uso |
|---|---|---|
| `editor.findMatchBackground` | `#a8d5a340` | Resultado atual da pesquisa (25%) |
| `editor.findMatchHighlightBackground` | `#99c79466` | Outros resultados da pesquisa (40%) |
| `editor.findRangeHighlightBackground` | `#99c79426` | Área de pesquisa delimitada (15%) |
| `editor.selectionBackground` | `#a8d5a307` | Texto selecionado (aprox. 3%, valor da última versão aprovada) |
| `editor.selectionHighlightBackground` | `#99c79466` | Ocorrências iguais não selecionadas (40%) |
| `editorMultiCursor.primary.foreground` | `#b0ff66bf` | Cursor principal em multisseleção (75%) |
| `editorMultiCursor.secondary.foreground` | `#b0ff66bf` | Cursores secundários (75%) |

O cursor único continua laranja (`editorCursor.foreground`). O destaque da linha permanece inalterado (`editor.lineHighlightBackground`). As cores são compartilhadas entre comandos: pesquisa também afeta Ctrl+F; seleção também afeta seleções comuns. Não há fundo separado para seleção principal e secundárias.

## Preservação da base

Todos os scopes, regras `tokenColors`, cores semânticas e demais propriedades foram preservados exatamente como dados na pasta fornecida. Apenas sete propriedades de interface foram ajustadas; duas delas foram acrescentadas para cursores múltiplos. Não houve tentativa de corrigir scopes por suposição.

O arquivo `REFERENCIA-ORIGINAL.md` conserva a documentação de transposição anterior como referência histórica; suas tabelas descrevem a base, não os ajustes atuais.
