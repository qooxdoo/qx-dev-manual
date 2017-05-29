# qooxdoo.org Website #

*(status: Not yet updated for 6.0 release)*

## General ##

<dl>
  <dt>The website `qooxdoo.org <http : //qooxdoo.org>`_ comprises of three distinct sub systems with the same look and feel. They share the header (with the main navigation) and footer (with the sub navigation). Changes to header or footer must be synced to all sub systems.</dt>
  <dd>
    <p>* **Wiki** (Dokuwiki): The home page and all other content not part of the remaining sub-systems mentioned below.</p>
    <p>* **Blog** (Wordpress): News and comments.</p>
    <p>* **Manual** (Sphinx): The qooxdoo manual is heavily linked from the Website. Direct links should generally point to the current version of the qooxdoo manual.</p>
  </dd>
</dl>
Another sub system is **Bugs** (Bugzilla). It has a similiar theme but does not share header or footer.

Moreover, the website points to tools, demo apps and downloadable assets found on `demo.qooxdoo.org <http://demo.qooxdoo.org>`_.

## Assets ##

All sub systems retrieve stylesheets and script files from the `resources <http://resources.qooxdoo.org>`_ host. See :doc:`resources.qooxdoo.org` for more information.

## Screenshots ##

For overall consistency, screenshots should be made with anti-aliasing turned on.

### Thumbnails ###

Thumbnails of screenshots are used on the `demos <http://qooxdoo.org/demos>`_ and `tools <http://qooxdoo.org/demos/tools>`_ page. The thumbnails dimensions are 285px/177px. Their scale factor is 0.5 compared to the original screenshot.

## Sub-pages ##

<dl>
  <dt>.. toctree :  : </dt>
  <dd>
    <p>:maxdepth: 1</p>
    <p>resources.qooxdoo.org</p>
  </dd>
</dl>
