Pages
=====

The structure of the Sphinx source code web pages, starting from 
``/usr/local/RATools`` is as follows::

  RATools
    source
      index.rst
        Contents:
        |- aboutastronomy -------> ../../Astronomy/README.rst
        |- aboutastrophysics ----> ../../Astrophysics/README.rst
        |- aboutdatareduction
        |- aboutdatestimes           (and so on)
        |- aboutmath
        |- aboutphysics
        |- aboutradioastronomy
        |- aboutsupport ---------> ../../support/README.rst
        Resources:
        |- aboutgit
        |- aboutpages

In other words, the links in Contents point to the ``README.rst`` of each
package. The ``README.rst`` should contain a short description of the package
and links to both the package and the package's pages.
