:show-content:

=====
Pages
=====

Odoo allows you to create pages for your website and customize their contents and appearance to your
needs.

Page creation
=============

Website pages can be created from the **frontend** and from the **backend**. To create a new website
page, proceed as follows:

  #. - Either open the **Website** app, click :guilabel:`+ New` in the top-right corner, then select
       :guilabel:`Page`;
     - Or go to :menuselection:`Website --> Site --> Pages` and click :guilabel:`New`.
  #. Enter a :guilabel:`Page Title`; this title is used in the menu, as well as the page's URL.
  #. Disable :guilabel:`Add to menu` if the page should not appear in the menu.
  #. Click :guilabel:`Create`.
  #. Customize the page's contents and appearance using the Website Builder, then click
     :guilabel:`Save`.
  #. :ref:`Publish <website/un-publish-page>` the page.

Page management
===============

.. _website/un-publish-page:

Publishing/unpublishing pages
-----------------------------

Pages need to be published to make them accessible to website visitors. To publish or unpublish a
page, toggle the switch in the upper-right corner from :guilabel:`Unpublished` to
:guilabel:`Published`, or vice versa.

.. image:: pages/un-published_toggle.png
   :alt: Unpublished/Published toggle

.. tip::
   It is also possible to:

    - publish/unpublish a page from the :ref:`page properties <website/page_properties>`, where you
      can define a publishing date and/or restrict the page's visibility if needed;
    - publish/unpublish several pages at once: Go to :menuselection:`Website --> Site --> Pages`,
      select the pages, then, click :guilabel:`Action` and select :guilabel:`Publish` or
      :guilabel:`Unpublish`.

Homepage
--------

By default, when you create a website, Odoo creates a dedicated homepage for it with the
:guilabel:`Page Title` "Home" and the :guilabel:`Page URL` "/". However, you can define any of your
website's pages as your homepage. To define a page as your homepage, open the desired page, then go
to :menuselection:`Website --> Site --> Properties`. In the :guilabel:`Publish` tab, enable
:guilabel:`Use as Homepage`.

.. note::
   Alternatively, you can modify your website's homepage in the website settings. Go to
   :menuselection:`Website --> Configuration --> Settings`, then, in the :guilabel:`Website info`
   section, define the URL of the desired page in the field :guilabel:`Homepage URL`.

.. _website/page_properties:

Page properties
---------------

To modify a page's properties, access the page you wish to modify, then go to
:menuselection:`Website --> Site --> Properties`.

The :guilabel:`Name` tab allows you to:

- rename the page using the :guilabel:`Page Name` field;
- modify the :guilabel:`Page URL`. In this case, you can :ref:`redirect the old URL to the new one
  <website/URL-redirection>`. To do so, enable :guilabel:`Redirect Old URL`, then select the
  :guilabel:`Type` of redirection.

  .. image:: pages/page-redirection.png
     :alt: Redirect old URL

You can further adapt the page's properties in the :guilabel:`Publish`: tab:

- :guilabel:`Show in Top Menu`: Enable if you want the page to appear in the menu;
- :guilabel:`Use as Homepage`: Enable if you want the page to be the homepage of your website;
- :guilabel:`Indexed`: Enable if you want the page to be indexed, i.e., shown in search engine
  results;
- :guilabel:`Published`: Enable to publish the page;
- :guilabel:`Publishing Date`: To publish the page at a specific moment, select the date,
  click the clock icon to set the time, then click the green tick to validate your selection.
- :guilabel:`Visibility`: Select who can access the page:

  - :guilabel:`All`
  - :guilabel:`Signed In`
  - :guilabel:`Restricted Group`: Select the group in the :guilabel:`Authorized group` field.
  - :guilabel:`With Password` : Enter the password in the :guilabel:`Password` field.

Alternatively, *some* of these properties can also be modified from :menuselection:`Website --> Site
--> Pages`.

Duplicating pages
~~~~~~~~~~~~~~~~~

To duplicate a page, access the page, then go to :menuselection:`Website --> Site --> Properties`
and click :guilabel:`Duplicate Page`. Enter a :guilabel:`Page Name`, then click :guilabel:`OK`.
By default, the new page is added to the menu, but you can remove it if needed.

.. _website/delete-page:

Deleting pages
~~~~~~~~~~~~~~

To delete a page, proceed as follows:

#. Access the page, then go to :menuselection:`Website --> Site --> Properties` and click
   :guilabel:`Delete Page`.
#. A pop-up window appears on the screen with all links referring to the page you want to delete,
   organized by category. Expand a category, e.g., :guilabel:`Page`, then click on a link to open
   it in a new window.
#. When you have updated all links, select the :guilabel:`I am sure about this` check box, then
   click :guilabel:`OK`.

.. note::
   Visitors are redirected to a 404 error page when they try to access a deleted page, either
   directly or through a link that hasn't been updates. You can prevent this by defining a
   :ref:`redirection <website/URL-redirection>` for the page's URL.

.. _website/URL-redirection:

URL redirects
-------------

Redirecting URLs consists in sending visitors and search engines to a URL that is different from the
one they originally requested. This technique is used, for example, to prevent broken links when you
:ref:`delete a page <website/delete-page>`, :ref:`modify its URL <website/page_properties>`, or move
your site to a new :doc:`domain </administration/maintain/domain_names>`. It can also be used to
improve :doc:`pages/seo`.

To access existing URL redirections for your website and create new ones, :doc:`activate the
developer mode </applications/general/developer_mode>` and go to :menuselection:`Website -->
Configuration --> Redirects`.

.. note::
   A record is added automatically everytime you :ref:`modify a page's URL <website/page_properties>`
   and enable :guilabel:`Redirect Old URL`.

To create a new redirection, click the :guilabel:`New` button, then fill in the fields:

- :guilabel:`Name`: Enter the name of the page;
- :guilabel:`Action`: Select the type of redirection:

   - 404 Not found: visitors are redirected to a 404 error page when they try to access the page.
     This can be useful for example if you have :doc:`multiple websites <configuration/multi_website>`
     and don't want the page of a website-related app (e.g. the **Shop** page for Odoo eCommerce)
     to be published on a specific website.
   - 301 Moved Permanently: for permanent redirections; the new URL is showed in search engine
     results and the redirect is performed immediately the next time without needing to fetch the original URL
     again (until the cache is cleared).
   - 302 Moved Temporarily: for short-term redirections, for example if you are redesigning or
     updating the page. The new URL is neither cached by browsers, nor shown in search engine
     results.
   - 308 Redirect / Rewrite: for permanent redirections; this is similar to a 301 redirect, but XXX

- :guilabel:`URL from`: Enter the URL to be redirected (e.g., `/about-the-company`)
- :guilabel:`URL to`; Enter the URL to be redirected to. If you want to redirect to an external URL,
  make sure to include the protocol (e.g. `https://`).
- :guilabel:`Website`: Select a specific website.

.. important::
   Before redirecting a page, you have to :ref:`unpublish <website/un-publish-page>` or
   :ref:`delete <website/delete-page>` it.

.. tip::
   Toggle the :guilabel:`Activate` switch if you wish to deactivate the redirection.

.. seealso::
   - `Redirects and Google Search <https://developers.google.com/search/docs/crawling-indexing/301-redirects>`_
   - :doc:`pages/seo`

.. toctree::
   :titlesonly:

   pages/seo
