======
Mixins
======
.. versionadded:: 1.0.0
Mixins are abstract NodeTypes that can not be used directly. Abstract NodeTypes are great to create some definitions that
could easily be reused by other NodeType definitions though we are reducing the amount of definitions overall.

Mixin is just a naming convention to describe what these NodeTypes actually do.

The default NodeTypes package provides the following NodeType Mixin:


TYPO3.Neos.NodeTypes:TitleMixin
-------------------------------
providing a property to use as a inline editable headline inside any NodeType
::

    'TYPO3.Neos.NodeTypes:TitleMixin':
      abstract: TRUE
      properties:
        title:
          type: string
          defaultValue: '<h1>Enter headline here</h1>'
          ui:
            inlineEditable: TRUE
            aloha:
              'format':
                'p': FALSE
                'h1': TRUE
                'h2': TRUE
                'h3': TRUE
                'removeFormat': TRUE
              'link':
                'a': TRUE

TYPO3.Neos.NodeTypes:TextMixin
------------------------------
proving a text property with full rte inline editable support
::

    'TYPO3.Neos.NodeTypes:TextMixin':
      abstract: TRUE
      properties:
        text:
          type: string
          defaultValue: ''
          ui:
            inlineEditable: TRUE
            aloha:
              placeholder: '<p>Enter text here</p>'
              autoparagraph: TRUE
              'format':
                'strong': TRUE
                'em': TRUE
                'u': FALSE
                'sub': FALSE
                'sup': FALSE
                'del': FALSE
                'p': TRUE
                'h1': TRUE
                'h2': TRUE
                'h3': TRUE
                'pre': TRUE
                'removeFormat': TRUE
              'table':
                'table': TRUE
              'list':
                'ol': TRUE
                'ul': TRUE
              'link':
                'a': TRUE

TYPO3.Neos.NodeTypes:ImageMixin
-------------------------------
providing three properties (image, alternativeText, title) to add single image support to other NodeTypes
::

    'TYPO3.Neos.NodeTypes:ImageMixin':
      abstract: TRUE
      ui:
        inspector:
          groups:
            image:
              label: 'Image'
              position: 5
      properties:
        image:
          type: TYPO3\Media\Domain\Model\ImageInterface
          ui:
            label: 'Image'
            reloadIfChanged: TRUE
            inspector:
              group: 'image'
              position: 50
        alternativeText:
          type: string
          ui:
            label: 'Alternative text'
            reloadIfChanged: TRUE
            inspector:
              group: 'image'
              position: 100
        title:
          type: string
          ui:
            label: 'Title'
            reloadIfChanged: TRUE
            inspector:
              group: 'image'
              position: 150

TYPO3.Neos.NodeTypes:ImageCaptionMixin
--------------------------------------
providing a hasCaption (checkbox style) and caption property
::

    'TYPO3.Neos.NodeTypes:ImageCaptionMixin':
      abstract: TRUE
      properties:
        hasCaption:
          type: boolean
          ui:
            label: 'Enable caption'
            reloadIfChanged: TRUE
            inspector:
              group: 'image'
              position: 200
        caption:
          type: string
          defaultValue: ''
          ui:
            inlineEditable: TRUE
            aloha:
              placeholder: '<p>Enter caption here</p>'
              autoparagraph: TRUE

TYPO3.Neos.NodeTypes:ImageAlignmentMixin
----------------------------------------
providing a property `alignment` (selectbox with options '', left, center, right)
::

    'TYPO3.Neos.NodeTypes:ImageAlignmentMixin':
      abstract: TRUE
      properties:
        alignment:
          type: string
          defaultValue: ''
          ui:
            label: 'Alignment'
            reloadIfChanged: TRUE
            inspector:
              group: 'image'
              position: 400
              editor: 'TYPO3.Neos/Inspector/Editors/SelectBoxEditor'
              editorOptions:
                placeholder: 'Default'
                values:
                  '':
                    label: ''
                  center:
                    label: 'Center'
                  left:
                    label: 'Left'
                  right:
                    label: 'Right'

TYPO3.Neos.NodeTypes:LinkMixin
------------------------------
providing a property **link** and integrates the link editor
::

    'TYPO3.Neos.NodeTypes:LinkMixin':
      abstract: TRUE
      properties:
        link:
          type: string
          ui:
            label: 'Link'
            reloadIfChanged: TRUE
            inspector:
              position: 300
              editor: 'TYPO3.Neos/Inspector/Editors/LinkEditor'

TYPO3.Neos.NodeTypes:ContentImageMixin
--------------------------------------
combining the Image, Image caption, Image Alignment and Link Mixin and configuring a inspector image group
::

    'TYPO3.Neos.NodeTypes:ContentImageMixin':
      abstract: TRUE
      superTypes:
        'TYPO3.Neos.NodeTypes:ImageMixin': TRUE
        'TYPO3.Neos.NodeTypes:LinkMixin': TRUE
        'TYPO3.Neos.NodeTypes:ImageCaptionMixin': TRUE
        'TYPO3.Neos.NodeTypes:ImageAlignmentMixin': TRUE
      properties:
        link:
          ui:
            inspector:
              group: 'image'
