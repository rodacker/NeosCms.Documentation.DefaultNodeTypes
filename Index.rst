====================================
Neos default NodeTypes Documentation
====================================
.. versionadded:: 1.0.0
Neos ships with a package called *TYPO3.Neos.NodeTypes* which provides a base layer of common NodeTypes to get you stared with adding structured content to your website.

We assume you know the basic concept of nodes within Neos. If not, please at first read the documentatio about the concept ```What is a node?```.

We are distinguishing two different type of nodes.


An important distinction is between nodes which look and behave like pages and "normal content" such as text, which is rendered inside a page.
Nodes which behave like pages are called Document Nodes in Neos. This means they have a unique, externally visible URL by which they can be rendered.

.. toctree::
   :maxdepth: 2

   Mixins
   Documents
   Content