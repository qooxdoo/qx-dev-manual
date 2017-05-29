# resources.qooxdoo.org #

Static assets like style sheets, scripts and images that are not controlled by
one of our subsystems (like the blog software) are served from
**resources.qooxdoo.org**. It also holds snapshots of our software or dedicated
downloads like patches.

CSS and JS files are maintained in our Git repository (see further). Those asset
files are not only used on our web sites, but also in manual.

## CSS ##

<dl>
  <dt>**/style**</dt>
  <dd>Old style sheets, still in use for http://attic.qooxdoo.org.</dd>
</dl>
<dl>
  <dt>**/stylesheets**</dt>
  <dd>Style sheets for the new homepage (apr'12).</dd>
</dl>
### Maintenance ###

These style sheets are maintained in our repository.

<dl>
  <dt>**tool/admin/www/resources/stylesheets**</dt>
  <dd>
    <p>Directory with CSS files as used online. This directory and its contents is</p>
    <p>copied to the production server. Files in this directory are under version</p>
    <p>control (although some of them are generated).</p>
  </dd>
</dl>
<dl>
  <dt>**tool/admin/www/resources/scss**</dt>
  <dd>Path to the .scss sources for (some of the) .css files in ``stylesheets/``.</dd>
</dl>
<dl>
  <dt>**make -f tool/admin/release/Makefile.release resources-build-css**</dt>
  <dd>
    <p>Make command to run the SCSS compiler and re-generate the CSS files in</p>
    <p>``stylesheets/`` that are maintained as .scss files. This command is</p>
    <p>automatically run with a ``publish-build``.</p>
  </dd>
</dl>
<dl>
  <dt>**make -f tool/admin/release/Makefile.release resources-publish**</dt>
  <dd>
    <p>Make command to publish resources (all, not just CSS) to the staging server.</p>
    <p>Run by ``publish-build``.</p>
  </dd>
</dl>
## JavaScript ##

<dl>
  <dt>**/javascripts**</dt>
  <dd>Script files for the new homepage (apr'12).</dd>
</dl>
### Maintenance ###

Script files used on our web sites are maintained in the repository.

<dl>
  <dt>**tool/admin/www/resources/javascripts**</dt>
  <dd>
    <p>Directory with JS files as used online. This directory and its contens is</p>
    <p>copied to the production server. Files in this directory are under version</p>
    <p>control (although some of them are copies from other paths).</p>
    <p>The directory contains third-party scripts that should be updated in place,</p>
    <p>keeping license files in sync.</p>
  </dd>
</dl>
<dl>
  <dt>**tool/admin/www/resources/q.website**</dt>
  <dd>
    <p>Self-written script code is maintained here. It contains a</p>
    <p>``qx.Website``-style skeleton structure.</p>
    <p>* **script**</p>
    <p>Contains a custom q library, where the range of framework classes is</p>
    <p>taylored towards what's needed on the web sites. Needs to be generated, with</p>
    <p>jobs ``q-build`` and ``q-build-min``. The q-build-min output is what gets</p>
    <p>used in ``javascripts/q.js``.</p>
    <p>* **source**</p>
    <p>Contains custom application files and q plugins, to be maintained here.</p>
    <p>* **test**</p>
    <p>Standard testrunner-portable environment, with adapted ``index.html``, so a</p>
    <p>dedicated ``script/q-<version>.min.js`` q library is loaded for the</p>
    <p>testrunner itself.</p>
    <p>* **index.html**</p>
    <p>Custom index.html to develop all the components, uses all scripts and styles</p>
    <p>also used online.</p>
  </dd>
</dl>
<dl>
  <dt>**make -f tool/admin/release/Makefile.release resources-build-js**</dt>
  <dd>
    <p>Make command to run the Generator, re-generate the q library, and copy it and</p>
    <p>all the .js files in ``source/`` to ``javascripts``. This command is *not*</p>
    <p>automatically run with a ``publish-build``, and has to be invoked directly.</p>
  </dd>
</dl>
<dl>
  <dt>**make -f tool/admin/release/Makefile.release resources-publish**</dt>
  <dd>
    <p>Make command to publish resources (all, not just JS) to the staging server.</p>
    <p>Run by ``publish-build``.</p>
  </dd>
</dl>
