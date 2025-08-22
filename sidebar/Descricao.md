# Descrição do Arquivo `sidebar.json`

Este arquivo JSON serve como a fonte de dados para a construção de um componente de barra de navegação lateral (sidebar) dinâmica. A estrutura foi projetada para ser flexível e permitir a criação de múltiplos grupos de navegação, cada um com seus próprios itens e subitens.

## Estrutura Principal do Objeto

O objeto JSON principal contém as seguintes chaves:

-   `arraySidebar`: (Array) O contêiner principal para todos os grupos de navegação.
-   `sideBarVerticalisExpanded`: (Boolean) Controla o estado de expansão da sidebar (se está expandida ou recolhida).
-   `sideBarVerticalSizeExpanded`: (Number) Define a largura da sidebar em pixels quando ela está no estado expandido.
-   `sideBarVerticalSizeCollapsed`: (Number) Define a largura da sidebar em pixels quando ela está no estado recolhido.
-   `typeSidebar`: (String) Define o tipo da sidebar (ex: "Vertical").

## Estrutura do `arraySidebar`

Este array contém múltiplos objetos, onde cada objeto representa um "grupo" de links na sidebar.

-   **Objeto de Grupo**:
    -   `titleGroup`: (String) O título do grupo, que serve como um cabeçalho para uma seção da sidebar (ex: "Grupo 1").
    -   `arrayItem`: (Array) Contém os itens de navegação pertencentes a este grupo.

## Estrutura do `arrayItem`

Cada objeto dentro deste array representa um item de navegação principal, que pode ou não ter subitens.

-   **Objeto de Item**:
-   `idItem`: (Number) Um identificador numérico único para o item.
-   `titleItem`: (String) O texto que será exibido para este item (atualmente padronizado como "item").
-   `icon`: (String) O nome de um ícone da biblioteca Phosphor Icons a ser exibido ao lado do título.
    -   `arraySubitem`: (Array) Contém os subitens de navegação associados a este item principal.

## Estrutura do `arraySubitem`

Cada objeto neste array representa um subitem de navegação, que é o link final.

-   **Objeto de Subitem**:
-   `idSubitem`: (Number) Um identificador numérico único para o subitem, geralmente no formato `[idItem].[index]`.
-   `titleSubitem`: (String) O texto que será exibido para o subitem (atualmente padronizado como "subitem").
-   `icon`: (String) O nome de um ícone da biblioteca Phosphor Icons a ser exibido ao lado do título.
    -   `objectSubitem`: (Object) Um objeto que contém metadados e configurações para o comportamento do link do subitem.
        -   `type`: (String) Tipo de ação ou link.
        -   `pageid`: (String) Identificador da página de destino.
        -   `sectionid`: (String/null) Identificador da seção específica na página de destino.
        -   `targetBlank`: (Boolean) Define se o link deve ser aberto em uma nova aba (`true`) ou não (`false`).
        -   `loadProgress`: (Boolean) Indica se uma barra de progresso de carregamento deve ser exibida.
        -   `loadprogressColors`: (String/null) Cores para a barra de progresso.
