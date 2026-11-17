# Transposição Mariana + Default Dark (Sublime Text → VS Code)

## Origem e método
- `Mariana color scheme(1).sublime-color-scheme`: paleta, estados do editor e realce de sintaxe.
- `Default Dark theme(1).sublime-theme`: barras, abas, menus, títulos e demais elementos de interface.
- `Theme configuration for VS Code(1).jsonc`: estrutura de propriedades do VS Code, preservada como catálogo comentado na versão editável.
- Valores em HSL/HSLA e expressões `var()` do arquivo do Sublime foram convertidos para `#RRGGBB`/`#RRGGBBAA`.
- `semanticHighlighting` fica desativado para evitar que classes semânticas do VS Code substituam os escopos TextMate do Mariana.

## Paleta do Mariana — valores calculados a partir do arquivo enviado

| Variável Sublime | Declaração original | Cor convertida |
|---|---|---|
| `black` | `hsl(0, 0%, 0%)` | `#000000` |
| `blue` | `hsl(210, 50%, 60%)` | `#6699CC` |
| `blue-vibrant` | `hsl(210, 60%, 60%)` | `#5C99D6` |
| `blue2` | `hsla(210, 13%, 40%, 0.7)` | `#596673B2` |
| `blue3` | `hsl(210, 15%, 22%)` | `#303841` |
| `blue4` | `hsl(210, 13%, 45%)` | `#647382` |
| `blue5` | `hsl(180, 36%, 54%)` | `#5FB4B4` |
| `blue6` | `hsl(221, 12%, 69%)` | `#A6ACB9` |
| `green` | `hsl(114, 31%, 68%)` | `#99C794` |
| `grey` | `hsl(0, 0%, 20%)` | `#333333` |
| `orange` | `hsl(32, 93%, 66%)` | `#F9AE58` |
| `orange2` | `hsl(32, 85%, 55%)` | `#EE932B` |
| `orange3` | `hsl(40, 94%, 68%)` | `#FAC761` |
| `pink` | `hsl(300, 30%, 68%)` | `#C695C6` |
| `red` | `hsl(357, 79%, 65%)` | `#EC5F66` |
| `red2` | `hsl(13, 93%, 66%)` | `#F97B58` |
| `white` | `hsl(0, 0%, 100%)` | `#FFFFFF` |
| `white2` | `hsl(0, 0%, 97%)` | `#F7F7F7` |
| `white3` | `hsl(219, 28%, 88%)` | `#D8DEE9` |

## Elementos globais do editor

| Propriedade do Sublime | Valor original | Destino principal no VS Code |
|---|---|---|
| `foreground` | `var(white3)` | editor.foreground |
| `background` | `var(blue3)` | editor.background |
| `accent` | `var(blue-vibrant)` | focusBorder / activityBar.activeBorder |
| `caret` | `var(orange)` | editorCursor.foreground |
| `line_highlight` | `var(blue2)` | editor.lineHighlightBackground |
| `selection` | `var(blue2)` | editor.selectionBackground |
| `selection_border` | `var(blue4)` | sem correspondente de borda da seleção; editor.selectionBackground cobre somente o preenchimento |
| `inactive_selection` | `var(blue2)` | editor.inactiveSelectionBackground |
| `misspelling` | `var(red)` | editorError.foreground (aproximação) |
| `shadow` | `color(var(black) alpha(0.25))` | widget.shadow / scrollbar.shadow |
| `active_guide` | `var(blue5)` | editorIndentGuide.activeBackground1 |
| `stack_guide` | `color(var(blue5) alpha(0.5))` | editorBracketPairGuide.background1 |
| `highlight` | `var(blue5)` | editor.selectionHighlightBackground |
| `find_highlight_foreground` | `var(grey)` | sem equivalente em editor.findMatch (a cor do texto não é configurável) |
| `find_highlight` | `var(orange3)` | editor.findMatchBackground |
| `brackets_options` | `underline` | aproximação: editorBracketMatch.border |
| `brackets_foreground` | `var(orange)` | editorBracketMatch.border |
| `bracket_contents_options` | `underline` | sem equivalente de underline direto |
| `bracket_contents_foreground` | `var(blue5)` | editorBracketHighlight.foreground2 |
| `tags_options` | `stippled_underline` | sem equivalente de sublinhado pontilhado |
| `tags_foreground` | `var(pink)` | sem equivalente para sublinhado de tags; entity.name.tag é regra separada (vermelha) |

## Valores explícitos de Default Dark

| Propriedade Sublime | Expressão original | Cor convertida (quando resolvível) |
|---|---|---|
| `base_hue` | `hsl(215, 10%, 50%)` | `#737D8C` |
| `base_tint` | `white` | `#FFFFFF` |
| `ui_bg` | `color(var(base_hue) l(20%))` | `#2E3238` |
| `text_fg` | `hsl(0, 0%, 85%)` | `#D9D9D9` |
| `link_fg` | `hsl(215, 45%, 65%)` | `#7E9FCE` |
| `button_bg` | `color(var(base_hue) l(30%))` | `#454B54` |
| `button_label_shadow` | `transparent` | `#00000000` |
| `sidebar_bg` | `color(var(base_hue) l(15%))` | `#22262A` |
| `sidebar_row_selected` | `color(var(base_hue) l(25%))` | `#393F46` |
| `sidebar_heading` | `hsl(0, 0%, 90%)` | `#E6E6E6` |
| `sidebar_heading_shadow` | `transparent` | `#00000000` |
| `sidebar_label` | `hsl(0, 0%, 80%)` | `#CCCCCC` |
| `sidebar_label_selected` | `hsl(0, 0%, 90%)` | `#E6E6E6` |
| `sidebar_label_ignored` | `hsl(0, 0%, 50%)` | `#808080` |
| `sidebar_scroll_bar_bg` | `var(scroll_bar_dark_bg)` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `sidebar_scroll_bar_puck_bg` | `var(scroll_bar_puck_dark_bg)` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `panel_bg` | `var(ui_bg)` | `#2E3238` |
| `progress_bar_fg` | `color(var(base_hue) l(40%))` | `#5C6470` |
| `dialog_button_bg` | `color(var(base_hue) l(50%))` | `#737D8C` |
| `icon_button_highlight` | `color(var(base_hue) l(30%))` | `#454B54` |
| `tool_tip_fg` | `hsl(0, 0%, 25%)` | `#404040` |
| `tabset_dark_tint_mod` | `color(white a(0.20))` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `tabset_dark_bg` | `color(var(--background) blend(white 80%))` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `tabset_medium_dark_tint_mod` | `color(white a(0.15))` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `tabset_medium_dark_bg` | `color(var(--background) blend(white 85%))` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `tabset_medium_tint_mod` | `color(black a(0.25))` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `tabset_medium_bg` | `color(var(--background) blend(black 75%))` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `tabset_light_tint_mod` | `color(black a(0.20))` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `tabset_light_bg` | `color(var(--background) blend(black 80%))` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `overlay_bg` | `var(ui_bg)` | `#2E3238` |
| `quick_panel_label_color` | `color(var(base_hue) l(75%))` | `#B9BEC6` |
| `quick_panel_path_label_color` | `color(var(base_hue) l(65%))` | `#9DA4AF` |
| `quick_panel_matched_label_color` | `color(var(base_hue) l(90%))` | `#E3E5E8` |
| `quick_panel_matched_path_label_color` | `color(var(base_hue) l(80%))` | `#C7CBD1` |
| `quick_panel_selected_row_bg` | `color(var(base_hue) l(30%))` | `#454B54` |
| `quick_panel_selected_label_color` | `color(var(base_hue) l(80%))` | `#C7CBD1` |
| `quick_panel_selected_path_label_color` | `color(var(base_hue) l(70%))` | `#ABB1BA` |
| `quick_panel_selected_matched_label_color` | `var(quick_panel_matched_label_color)` | `#E3E5E8` |
| `quick_panel_selected_matched_path_label_color` | `color(var(base_hue) l(80%))` | `#C7CBD1` |
| `status_bar_bg` | `var(ui_bg)` | `#2E3238` |
| `status_bar_label_shadow` | `transparent` | `#00000000` |
| `file_tab_angled_unselected_dark_tint` | `color(white a(0.07))` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `file_tab_angled_unselected_medium_dark_tint` | `color(white a(0.07))` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `file_tab_angled_unselected_medium_tint` | `color(black a(0.13))` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `file_tab_angled_unselected_light_tint` | `color(black a(0.12))` | `depende de `Default.sublime-theme` ou de estado do Sublime` |
| `file_tab_angled_unselected_label_color` | `hsl(0, 0%, 60%)` | `#999999` |
| `file_tab_angled_unselected_label_shadow` | `transparent` | `#00000000` |
| `file_tab_angled_unselected_medium_label_color` | `hsl(0, 0%, 75%)` | `#BFBFBF` |
| `file_tab_angled_unselected_medium_label_shadow` | `transparent` | `#00000000` |
| `file_tab_angled_unselected_light_label_color` | `hsl(0, 0%, 45%)` | `#737373` |
| `file_tab_angled_unselected_light_label_shadow` | `transparent` | `#00000000` |
| `radio_back` | `var(--background)` | `#303841` |
| `radio_selected` | `var(--bluish)` | `#5C99D6` |
| `radio_border-selected` | `var(--bluish)` | `#5C99D6` |
| `checkbox_back` | `var(--background)` | `#303841` |
| `checkbox_selected` | `var(--bluish)` | `#5C99D6` |
| `checkbox_border-selected` | `var(--bluish)` | `#5C99D6` |

## Regras de sintaxe

Cada uma das 63 regras foi transposta para `tokenColors` na ordem de origem. Algumas regras com exclusões (`-`) ou alternativas (`|`) receberam seletores TextMate compatíveis com o VS Code. Quatro regras adicionais de exceção impedem que uma categoria ampla sobreponha os casos especiais.

| Nº | Nome original | Scope Sublime | Scope VS Code |
|---|---|---|---|
| 1 | Comment | `comment, punctuation.definition.comment` | `comment, punctuation.definition.comment` |
| 2 | String | `string` | `string` |
| 3 | String Key | `meta.mapping.key string - meta.mapping.key meta meta \| meta.mapping.key meta.mapping.key string - meta.mapping.key meta.mapping.key meta meta` | `meta.mapping.key string, meta.mapping.key meta.mapping.key string` |
| 4 | Punctuation | `punctuation.definition - punctuation.definition.numeric.base` | `punctuation.definition` |
| 5 | Number | `constant.numeric` | `constant.numeric` |
| 6 | Number Suffix | `storage.type.numeric` | `storage.type.numeric` |
| 7 | Built-in constant | `constant.language` | `constant.language` |
| 8 | User-defined constant | `constant.character, constant.other` | `constant.character, constant.other` |
| 9 | Member Variable | `variable.member` | `variable.member` |
| 10 | Keyword | `keyword - keyword.operator, keyword.operator.word` | `keyword, keyword.operator.word` |
| 11 | Operators | `keyword.operator` | `keyword.operator` |
| 12 | Punctuation | `punctuation.separator, punctuation.terminator` | `punctuation.separator, punctuation.terminator` |
| 13 | Punctuation | `punctuation.section` | `punctuation.section` |
| 14 | Accessor | `punctuation.accessor` | `punctuation.accessor` |
| 15 | Annotation Punctuation | `punctuation.definition.annotation` | `punctuation.definition.annotation` |
| 16 | JavaScript Dollar | `variable.other.dollar.only.js, variable.other.object.dollar.only.js, variable.type.dollar.only.js, support.class.dollar.only.js` | `variable.other.dollar.only.js, variable.other.object.dollar.only.js, variable.type.dollar.only.js, support.class.dollar.only.js` |
| 17 | Storage | `storage` | `storage` |
| 18 | Storage type | `storage.type` | `storage.type` |
| 19 | Entity name | `entity.name.function` | `entity.name.function` |
| 20 | Entity name | `entity.name - (entity.name.section \| entity.name.tag \| entity.name.label)` | `entity.name` |
| 21 | Inherited class | `entity.other.inherited-class` | `entity.other.inherited-class` |
| 22 | Function argument | `variable.parameter` | `variable.parameter` |
| 23 | Language variable | `variable.language` | `variable.language` |
| 24 | Tag name | `entity.name.tag` | `entity.name.tag` |
| 25 | Tag attribute | `entity.other.attribute-name` | `entity.other.attribute-name` |
| 26 | Function call | `variable.function, variable.annotation` | `variable.function, variable.annotation` |
| 27 | Library function | `support.function, support.macro` | `support.function, support.macro` |
| 28 | Library constant | `support.constant` | `support.constant` |
| 29 | Library class/type | `support.type, support.class` | `support.type, support.class` |
| 30 | Invalid | `invalid` | `invalid` |
| 31 | Invalid deprecated | `invalid.deprecated` | `invalid.deprecated` |
| 32 | YAML Key | `entity.name.tag.yaml` | `entity.name.tag.yaml` |
| 33 | YAML String | `source.yaml string.unquoted` | `source.yaml string.unquoted` |
| 34 | markup headings | `markup.heading` | `markup.heading` |
| 35 | markup headings | `markup.heading punctuation.definition.heading` | `markup.heading punctuation.definition.heading` |
| 36 | markup h1 | `markup.heading.1 punctuation.definition.heading` | `markup.heading.1 punctuation.definition.heading` |
| 37 | markup links | `string.other.link, markup.underline.link` | `string.other.link, markup.underline.link` |
| 38 | markup bold | `markup.bold` | `markup.bold` |
| 39 | markup italic | `markup.italic` | `markup.italic` |
| 40 | markup underline | `markup.underline` | `markup.underline` |
| 41 | markup bold/italic | `markup.italic markup.bold \| markup.bold markup.italic` | `markup.italic markup.bold, markup.bold markup.italic` |
| 42 | markup bold/underline | `markup.underline markup.bold \| markup.bold markup.underline` | `markup.underline markup.bold, markup.bold markup.underline` |
| 43 | markup italic/underline | `markup.underline markup.italic \| markup.italic markup.underline` | `markup.underline markup.italic, markup.italic markup.underline` |
| 44 | markup bold/italic/underline | `markup.bold markup.italic markup.underline \| markup.bold markup.underline markup.italic \| markup.italic markup.bold markup.underline \| markup.italic markup.underline markup.bold \| markup.underline markup.bold markup.italic \| markup.underline markup.italic markup.bold` | `markup.bold markup.italic markup.underline, markup.bold markup.underline markup.italic, markup.italic markup.bold markup.underline, markup.italic markup.underline markup.bold, markup.underline markup.bold markup.italic, markup.underline markup.italic markup.bold` |
| 45 | markup hr | `punctuation.definition.thematic-break` | `punctuation.definition.thematic-break` |
| 46 | markup numbered list bullet | `markup.list.numbered.bullet` | `markup.list.numbered.bullet` |
| 47 | markup blockquote | `markup.quote punctuation.definition.blockquote, markup.list punctuation.definition.list_item` | `markup.quote punctuation.definition.blockquote, markup.list punctuation.definition.list_item` |
| 48 | markup code | `markup.raw` | `markup.raw` |
| 49 | markup code | `markup.raw.inline` | `markup.raw.inline` |
| 50 | markup punctuation | `(text punctuation.definition.italic \| text punctuation.definition.bold)` | `(text punctuation.definition.italic, text punctuation.definition.bold)` |
| 51 | diff.header | `meta.diff, meta.diff.header` | `meta.diff, meta.diff.header` |
| 52 | diff.deleted | `markup.deleted` | `markup.deleted` |
| 53 | diff.inserted | `markup.inserted` | `markup.inserted` |
| 54 | diff.changed | `markup.changed` | `markup.changed` |
| 55 | CSS Properties | `support.type.property-name` | `support.type.property-name` |
| 56 | (sem nome) | `constant.numeric.line-number.match` | `constant.numeric.line-number.match` |
| 57 | (sem nome) | `message.error` | `message.error` |
| 58 | (sem nome) | `message.warning` | `message.warning` |
| 59 | (sem nome) | `message.info` | `message.info` |
| 60 | (sem nome) | `diff.deleted` | `diff.deleted` |
| 61 | (sem nome) | `diff.deleted.char` | `diff.deleted.char` |
| 62 | (sem nome) | `diff.inserted` | `diff.inserted` |
| 63 | (sem nome) | `diff.inserted.char` | `diff.inserted.char` |

## Limitações e aproximações

1. O arquivo `Default Dark theme(1).sublime-theme` **herda** `Default.sublime-theme`. As regras e variáveis herdadas não foram fornecidas. Valores como `var(--bluish)`, `scroll_bar_dark_bg` e `scroll_bar_puck_dark_bg` não têm definição explícita no arquivo reenviado. Cores equivalentes do Mariana (principalmente `accent`) foram utilizadas apenas nos componentes relevantes.
2. Alguns estilos do Sublime — abas inclinadas, sombras de rótulo, sublinhado pontilhado e regras de desenho de widgets — não podem ser reproduzidos somente com um tema de cores do VS Code.
3. `foreground_adjust` das quatro regras de diff não possui conversão direta; as cores translúcidas de fundo são preservadas nas regras, mas o VS Code pode ignorar os fundos em `tokenColors`. As cores de diff do editor receberam aproximação explícita.
4. A gramática de syntax e a associação de escopos variam conforme a linguagem e as extensões de cada editor. A mesma cor no mesmo escopo não garante idêntico resultado por linguagem.
5. Alguns controles modernos e ícones do VS Code não existem no arquivo de tema do Sublime Text; nesses casos, as cores de interface foram derivadas de `ui_bg`, `sidebar_bg`, `text_fg` e `accent`, sem inventar uma nova paleta.
6. `colors` do arquivo de tema não altera tipografia, espaçamentos, ícones, disposição de janelas ou as preferências de editor.

## Instalação

- **VSIX:** em VS Code, abra Extensões, menu `...`, opção **Instalar a partir de VSIX...**, escolha o arquivo `.vsix` e selecione o tema em `Ctrl+K`, `Ctrl+T`.
- **Pasta:** descompacte o `.zip` na pasta de extensões do VS Code (geralmente `~/.vscode/extensions/` no Linux; `%USERPROFILE%\.vscode\extensions\` no Windows), deixando `package.json` na raiz da pasta extraída. Reinicie ou recarregue o VS Code.
- **Edição:** altere o `.editavel.jsonc`; para usar as alterações como tema, copie os valores para o `themes/Mariana-Default-Dark.color-theme.json` da extensão (o JSON da extensão não admite comentários).

## Resumo quantitativo

- **19** cores base (Mariana) declaradas.
- **57** variáveis de interface Default Dark declaradas.
- **63** regras originais Mariana.
- **67** regras geradas para VS Code (inclui 4 ajustes de compatibilidade).
- **294** cores de interface ativas no VS Code.
- **576** exemplos originais de propriedades do VS Code preservados como comentários.
