==================
Document NodeTypes
==================
.. versionadded:: 1.0.0
The package provides one Document NodeType and that is the **Page** NodeType including properties for a
layout and a subpageLayout.


TYPO3.Neos.NodeTypes:Page
-------------------------
::

    'TYPO3.Neos.NodeTypes:Page':
      superTypes:
        'TYPO3.Neos:Document': TRUE
      childNodes:
        main:
          type: 'TYPO3.Neos:ContentCollection'
      properties:
        layout:
          type: string
          ui:
            label: 'Layout for this page only'
            reloadIfChanged: TRUE
            inspector:
              group: ~
              editor: 'TYPO3.Neos/Inspector/Editors/SelectBoxEditor'
              editorOptions:
                placeholder: 'Inherit from parent'
                values:
                  '':
                    label: ''
        subpageLayout:
          type: string
          ui:
            label: 'Layout for subpages of this page'
            inspector:
              group: ~
              editor: 'TYPO3.Neos/Inspector/Editors/SelectBoxEditor'
              editorOptions:
                placeholder: 'Inherit from parent'
                values:
                  '':
                    label: ''
      ui:
        label: 'Page'
        icon: 'icon-file'
        position: 100
        inspector:
          groups:
            document:
              label: 'Title'
            layout:
              label: 'Layout'
              position: 150
