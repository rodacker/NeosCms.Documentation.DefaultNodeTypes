=================
Content NodeTypes
=================
.. versionadded:: 1.0.0
The packages provides a couple of Content NodeTypes:

TYPO3.Neos.NodeTypes:Headline
-----------------------------
::

    'TYPO3.Neos.NodeTypes:Headline':
      superTypes:
        'TYPO3.Neos:Content': TRUE
        'TYPO3.Neos.NodeTypes:TitleMixin': TRUE
      ui:
        label: 'Headline'
        icon: 'icon-font'
        position: 100

TYPO3.Neos.NodeTypes:Text
-------------------------
::

    'TYPO3.Neos.NodeTypes:Text':
      superTypes:
        'TYPO3.Neos:Content': TRUE
        'TYPO3.Neos.NodeTypes:TextMixin': TRUE
      ui:
        label: 'Text'
        icon: 'icon-file-text'
        position: 200

TYPO3.Neos.NodeTypes:Image
--------------------------
::
    'TYPO3.Neos.NodeTypes:Image':
      superTypes:
        'TYPO3.Neos:Content': TRUE
        'TYPO3.Neos.NodeTypes:ContentImageMixin': TRUE
      ui:
        label: 'Image'
        icon: 'icon-picture'
        position: 300

TYPO3.Neos.NodeTypes:TextWithImage
----------------------------------
::

    'TYPO3.Neos.NodeTypes:TextWithImage':
      superTypes:
        'TYPO3.Neos:Content': TRUE
        'TYPO3.Neos.NodeTypes:TextMixin': TRUE
        'TYPO3.Neos.NodeTypes:ContentImageMixin': TRUE
      ui:
        label: 'Text with Image'
        icon: 'icon-picture'
        position: 400

TYPO3.Neos.NodeTypes:Html
-------------------------
::

    'TYPO3.Neos.NodeTypes:Html':
      superTypes:
        'TYPO3.Neos:Content': TRUE
      ui:
        label: 'HTML'
        icon: 'icon-code'
        position: 500
        inspector:
          groups:
            html:
              label: 'HTML'
              position: 10
      properties:
        source:
          type: string
          ui:
            label: 'HTML Content'
            reloadIfChanged: TRUE
            inspector:
              group: 'html'
              editor: 'TYPO3.Neos/Inspector/Editors/CodeEditor'
              editorOptions:
                buttonLabel: 'Edit HTML source'
          defaultValue: '<p>Enter HTML here</p>'

TYPO3.Neos.NodeTypes:Menu
-------------------------
::

    'TYPO3.Neos.NodeTypes:Menu':
      superTypes:
        'TYPO3.Neos:Content': TRUE
      ui:
        label: 'Menu'
        group: 'structure'
        icon: 'icon-sitemap'
        position: 100
        inspector:
          groups:
            options:
              label: 'Options'
              position: 30
      properties:
        startLevel:
          type: string
          defaultValue: '0'
          ui:
            reloadIfChanged: TRUE
            label: 'Starting Level'
            inspector:
              group: 'options'
              editor: 'TYPO3.Neos/Inspector/Editors/SelectBoxEditor'
              editorOptions:
                values:
                  '-4':
                    label: 'Four Levels Above Current Page'
                  '-3':
                    label: 'Three Levels Above Current Page'
                  '-2':
                    label: 'Two Levels Above Current Page'
                  '-1':
                    label: 'One Level Above Current Page'
                  '0':
                    label: 'Same Level As Current Page'
                  '1':
                    label: 'First Level Of Website'
                  '2':
                    label: 'Second Level Of Website'
                  '3':
                    label: 'Third Level Of Website'
                  '4':
                    label: 'Fourth Level Of Website'
                  '5':
                    label: 'Fifth Level Of Website'
                  '6':
                    label: 'Sixth Level Of Website'
        selection:
          type: 'references'
          ui:
            reloadIfChanged: TRUE
            label: 'Selection'
            inspector:
              group: 'options'
        maximumLevels:
          type: string
          defaultValue: '1'
          ui:
            reloadIfChanged: TRUE
            label: 'Maximum Levels'
            inspector:
              group: 'options'
              editor: 'TYPO3.Neos/Inspector/Editors/SelectBoxEditor'
              editorOptions:
                values:
                  '1':
                    label: '1'
                  '2':
                    label: '2'
                  '3':
                    label: '3'
                  '4':
                    label: '4'
                  '5':
                    label: '5'
                  '6':
                    label: '6'
                  '7':
                    label: '7'
                  '8':
                    label: '8'
                  '9':
                    label: '9'
                  '10':
                    label: '10'

TYPO3.Neos.NodeTypes:Column
---------------------------
::

    'TYPO3.Neos.NodeTypes:Column':
      superTypes:
        'TYPO3.Neos:Content': TRUE
      abstract: TRUE
      ui:
        group: 'structure'
        label: 'Column'
        icon: 'icon-columns'
        inlineEditable: TRUE
        inspector:
          groups:
            column:
              label: 'Columns'
              position: 10
      properties:
        layout:
          type: string
          ui:
            label: 'Layout'
            inspector:
              group: 'column'
              editor: 'TYPO3.Neos/Inspector/Editors/SelectBoxEditor'

TYPO3.Neos.NodeTypes:TwoColumn
------------------------------
::

    'TYPO3.Neos.NodeTypes:TwoColumn':
      superTypes:
        'TYPO3.Neos.NodeTypes:Column': TRUE
      ui:
        label: 'Two column content'
        position: 200
      childNodes:
        column0:
          type: 'TYPO3.Neos:ContentCollection'
        column1:
          type: 'TYPO3.Neos:ContentCollection'
      properties:
        layout:
          defaultValue: '50-50'
          ui:
            reloadIfChanged: TRUE
            inspector:
              editorOptions:
                values:
                  '50-50':
                    label: '50% / 50%'
                  '75-25':
                    label: '75% / 25%'
                  '25-75':
                    label: '25% / 75%'
                  '66-33':
                    label: '66% / 33%'
                  '33-66':
                    label: '33% / 66%'

TYPO3.Neos.NodeTypes:ThreeColumn
--------------------------------
::

    'TYPO3.Neos.NodeTypes:ThreeColumn':
      superTypes:
        'TYPO3.Neos.NodeTypes:Column': TRUE
      ui:
        label: 'Three column content'
        position: 300
      childNodes:
        column0:
          type: 'TYPO3.Neos:ContentCollection'
        column1:
          type: 'TYPO3.Neos:ContentCollection'
        column2:
          type: 'TYPO3.Neos:ContentCollection'
      properties:
        layout:
          defaultValue: '33-33-33'
          ui:
            reloadIfChanged: TRUE
            inspector:
              editorOptions:
                values:
                  '33-33-33':
                    label: '33% / 33% / 33%'
                  '50-25-25':
                    label: '50% / 25% / 25%'
                  '25-50-25':
                    label: '25% / 50% / 25%'
                  '25-25-50':
                    label: '25% / 25% / 50%'

TYPO3.Neos.NodeTypes:FourColumn
-------------------------------
::

    'TYPO3.Neos.NodeTypes:FourColumn':
      superTypes:
        'TYPO3.Neos.NodeTypes:Column': TRUE
      ui:
        label: 'Four column content'
        position: 400
      childNodes:
        column0:
          type: 'TYPO3.Neos:ContentCollection'
        column1:
          type: 'TYPO3.Neos:ContentCollection'
        column2:
          type: 'TYPO3.Neos:ContentCollection'
        column3:
          type: 'TYPO3.Neos:ContentCollection'
      properties:
        layout:
          defaultValue: '25-25-25-25'
          ui:
            reloadIfChanged: TRUE
            inspector:
              editorOptions:
                values:
                  '25-25-25-25':
                    label: '25% / 25% / 25% / 25%'

TYPO3.Neos.NodeTypes:Form
-------------------------
::

    'TYPO3.Neos.NodeTypes:Form':
      superTypes:
        'TYPO3.Neos:Content': TRUE
      ui:
        label: 'Form'
        icon: 'icon-envelope-alt'
        position: 600
        inspector:
          groups:
            form:
              label: 'Form'
              position: 30
      properties:
        formIdentifier:
          type: string
          ui:
            label: 'Form identifier'
            reloadIfChanged: TRUE
            inspector:
              group: form
              editor: 'TYPO3.Neos/Inspector/Editors/SelectBoxEditor'
              editorOptions:
                placeholder: 'Select the Form identifier'
                values:
                  '':
                    label: ''

TYPO3.Neos.NodeTypes:AssetList
------------------------------
::

    'TYPO3.Neos.NodeTypes:AssetList':
      superTypes:
        'TYPO3.Neos:Content': TRUE
      ui:
        label: 'Asset list'
        icon: 'icon-folder-open-alt'
        position: 700
        inspector:
          groups:
            resources:
              label: 'Resources'
              position: 5
      properties:
        assets:
          type: array<TYPO3\Media\Domain\Model\Asset>
          ui:
            inspector:
              group: 'resources'
            label: 'Assets'
            reloadIfChanged: TRUE

TYPO3.Neos.NodeTypes:ContentReferences
--------------------------------------
::

    'TYPO3.Neos.NodeTypes:ContentReferences':
      superTypes:
        'TYPO3.Neos:Content': TRUE
      ui:
        label: 'Insert content references'
        icon: 'icon-copy'
        position: 800
        inspector:
          groups:
            references:
              label: 'References'
              position: 10
      properties:
        references:
          type: 'references'
          ui:
            inspector:
              group: 'references'
              editorOptions:
                nodeTypes: ['TYPO3.Neos:Content']
            label: 'Select'
            reloadIfChanged: TRUE


TYPO3.Neos.NodeTypes:Records
----------------------------
# DEPRECATED with Neos 1.2: This node type was renamed to "TYPO3.Neos.NodeTypes:ContentReferences"
::

    'TYPO3.Neos.NodeTypes:Records':
      superTypes:
        'TYPO3.Neos.NodeTypes:ContentReferences': TRUE
      abstract: TRUE
