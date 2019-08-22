**This is a heavily forked version of page-list by webvitaly. Main changes include:**

* Added `[topparent]` to show all children from the top-most ancestor
* Removed inline HTML comments
* Removed donation buttons
* Added `if_empty` and `list_id` as params for showing page lists. See documentation below.

=== Page-list ===
Contributors: webvitaly and Wes Foster (wesf90)
Tags: page, page-list, pagelist, sitemap, subpages, siblings
Requires at least: 3.0
Tested up to: 5.2
Stable tag: 5.1
License: GPLv3
License URI: http://www.gnu.org/licenses/gpl.html

[topparent], [pagelist], [subpages], [siblings] and [pagelist_ext] shortcodes

== Description ==

* **[Page-list](http://web-profile.net/wordpress/plugins/page-list/ "Plugin page")**
* **[all Page-list params](http://wordpress.org/plugins/page-list/other_notes/ "Page-list params")**
* **[Original GitHub](https://github.com/webvitalii/page-list "Fork")**

= shortcodes: =

* **[pagelist]** - hierarchical tree of all pages on site (useful to show sitemap of the site);
* **[subpages]** - hierarchical tree of subpages to the current page;
* **[topparent]** - hierarchical tree of subpages from the top-most parent;
* **[siblings]** - hierarchical tree of sibling pages to the current page;
* **[pagelist_ext]** - list of pages with featured image and with excerpt;

= examples with aditional parameters: =

* `[pagelist child_of="4" depth="2" exclude="6,7,8"]`
* `[pagelist_ext child_of="4" exclude="6,7,8" image_width="50" image_height="50"]`
* **[all Page-list params](http://wordpress.org/plugins/page-list/other_notes/ "Page-list params")**


== Other Notes ==

= Parameters for [pagelist], [subpages] and [siblings]: =
* **[pagelist]** - list of all pages as the hierarchical list;
* **[subpages]** - list of subpages to the current page as the hierarchical list; Same as: `[pagelist child_of="current"]`;
* **[siblings]** - list of sibling pages to the current page as the hierarchical list; Same as: `[pagelist child_of="parent"]`;
* **depth** - how many levels in the hierarchy of pages are to be included in the list: `[pagelist depth="3"]`; by default depth is unlimited (depth="0"); Displays pages at any depth and arranges them in a flat list: `[pagelist depth="-1"]`;
* **child_of** - displays the sub-pages of a single Page by ID: `[pagelist child_of="4"]`;
* **exclude** - define a comma-separated list of Page IDs to be excluded from the list: `[pagelist exclude="6,7,8"]`; You may exclude current page: `[pagelist exclude="current"]`;
* **exclude_tree** - define a comma-separated list of parent Page IDs and all its subpages to be excluded: `[pagelist exclude_tree="7,10"]`;
* **include** - include a comma-separated list of Page IDs into the list: `[pagelist include="6,7,8"]`;
* **title_li** - set the text and style of the Page list's heading: `[pagelist title_li="<h2>List of pages</h2>"]`; by default there is no title (title_li="");
* **authors** - only include pages authored by the authors in this comma-separated list of author IDs: `[pagelist authors="2,5"]`; by default all authors are included (authors="");
* **number** - sets the number of pages to display: `[pagelist number="10"]`; by default the number is unlimited (number="");
* **offset** - the number of pages to pass over (or displace) before collecting the set of pages: `[pagelist offset="5"]`; by default there is no offset (offset="");
* **post_type** - list associated with a certain hierarchical Post Type `[pagelist post_type="page"]`; by default: (post_type="page"); possible values: page, revision, Hierarchical Custom Post Types ('post' is not a Hierarchical Post Type);
* **post_status** - a comma-separated list of all post status types: `[pagelist post_status="private"]`; by default: (post_status="publish"); possible values: publish, private, draft;
* **meta_key** and **meta_value** - only include the pages that have this Custom Field Key and this Custom Field Value: `[pagelist meta_key="metakey" meta_value="metaval"]`;
* **show_date** - display creation or last modified date next to each Page: `[pagelist show_date="created"]`; possible values: created, modified, updated;
* **date_format** - the format of the Page date set by the show_date parameter: `[pagelist date_format="l, F j, Y"]`; by default use the date format configured in your WordPress options;
* **sort_column** - sort the list of pages by column: `[pagelist sort_column="menu_order"]`; by default: (sort_column="menu_order, post_title"); possible values: post_title, menu_order, post_date (sort by creation time), post_modified, ID, post_author, post_name (sort by page slug);
* **sort_order** - the sort order of the list of pages (either ascending or descending): `[pagelist sort_order="desc"]`; by default: (sort_order="asc"); possible values: asc, desc;
* **link_before** - sets the text or html that precedes the link text inside link tag: `[pagelist link_before="<span>"]`; you may specify html tags only in the `HTML` tab in your Rich-text editor;
* **link_after** - sets the text or html that follows the link text inside link tag: `[pagelist link_after="</span>"]`; you may specify html tags only in the `HTML` tab in your Rich-text editor;
* **class** - the CSS class for list of pages: `[pagelist class="listclass"]`; by default the class is empty (class="");
* **if_empty** - If the list returns nothing, you can enter a message here. Alternatively, you can enter `show_list_#` (where `#` is a number) to show a specific list if the current list returns empty.
* **list_id** - Use this on a list to hide it UNLESS it is triggered by an **if_empty**
* columns - for splitting list of pages into columns: `[pagelist class="page-list-cols-2"]`; available classes: page-list-cols-2, page-list-cols-3, page-list-cols-4, page-list-cols-5; works in all modern browsers and IE10+; columns are responsive and become 1 column at less than 768px;

More [info about params](http://codex.wordpress.org/Function_Reference/wp_list_pages#Parameters) for [pagelist], [subpages], [siblings].

= Parameters for [pagelist_ext]: =
* **[pagelist_ext]** - by default shows list of subpages to current page; but if there is no subpages than all pages will be shown;
* **show_image** - show or hide featured image `[pagelist_ext show_image="0"]`; "show_image" have higher priority than "show_first_image"; by default: show_image="1";
* **show_first_image** - show or hide first image from content if there is no featured image `[pagelist_ext show_first_image="1"]`; by default: show_first_image="0";
* **show_title** - show or hide title `[pagelist_ext show_title="0"]`; by default: show_title="1";
* **show_content** - show or hide content `[pagelist_ext show_content="0"]`; by default: show_content="1";
* **more_tag** - output all content before and after more tag: `[pagelist_ext more_tag="0"]`; this parameter does not add "more-link" to the end of content, it just cut content before more-tag; "more_tag" parameter have higher priority than "limit_content"; by default the more_tag is enabled (more_tag="1") and showing only content before more tag;
* **limit_content** - content is limited by "more-tag" if it is exist or by "limit_content" parameter `[pagelist_ext limit_content="100"]`; by default: limit_content="250";
* **image_width** - width of the image `[pagelist_ext image_width="80"]`; by default: image_width="50";
* **image_height** - height of the image `[pagelist_ext image_height="80"]`; by default: image_height="50";
* **child_of** - displays the sub-pages of a single Page by ID: `[pagelist_ext child_of="4"]`; by default it shows subpages to the current page;
* **parent** - list those pages that have the provided single page only ID as parent: `[pagelist_ext parent="4"]`; by default parent="-1" and depth is unlimited;
* **sort_column** - sort the list of pages by column: `[pagelist_ext sort_column="menu_order"]`; by default: (sort_column="menu_order, post_title"); possible values: post_title, menu_order, post_date (sort by creation time), post_modified, ID, post_author, post_name (sort by page slug);
* **sort_order** - the sort order of the list of pages (either ascending or descending): `[pagelist_ext sort_order="desc"]`; by default: (sort_order="asc"); possible values: asc, desc;* **hierarchical** - display subpages below their parent page `[pagelist_ext hierarchical="0"]`; by default: hierarchical="1";
* **hierarchical** - display subpages below their parent page `[pagelist_ext hierarchical="0"]`; by default: hierarchical="1";
* **exclude** - define a comma-separated list of Page IDs to be excluded from the list: `[pagelist_ext exclude="6,7,8"]`;
* **exclude_tree** - define a comma-separated list of parent Page IDs and all its subpages to be excluded: `[pagelist_ext exclude_tree="7,10"]`;
* **include** - include a comma-separated list of Page IDs into the list: `[pagelist_ext include="6,7,8"]`;
* **meta_key** and **meta_value** - only include the pages that have this Custom Field Key and this Custom Field Value: `[pagelist_ext meta_key="metakey" meta_value="metaval"]`;
* **authors** - only include the pages written by the given author(s) `[pagelist_ext authors="6,7,8"]`;
* **number** - sets the number of pages to display: `[pagelist_ext number="10"]`; by default the number is unlimited (number="");
* **offset** - the number of pages to pass over (or displace) before collecting the set of pages: `[pagelist_ext offset="5"]`; by default there is no offset (offset="");
* **post_type** - list associated with a certain hierarchical Post Type `[pagelist_ext post_type="page"]`; by default: (post_type="page"); possible values: page, revision, Hierarchical Custom Post Types ('post' is not a Hierarchical Post Type);
* **post_status** - a comma-separated list of all post status types: `[pagelist_ext post_status="private"]`; by default: (post_status="publish"); possible values: publish, private, draft;
* **class** - the CSS class for list of pages: `[pagelist_ext class="listclass"]`; by default the class is empty (class="");
* **strip_tags** - strip tags or not: `[pagelist_ext strip_tags="0"]`; by default the tags are stripped (strip_tags="1");
* **strip_shortcodes** - strip registered shortcodes or not: `[pagelist_ext strip_shortcodes="0"]`; by default shortcodes are stripped (strip_shortcodes="1") and all registered shortcodes are removed;
* **show_child_count** - show count of subpages: `[pagelist_ext show_child_count="1"]`; by default the child_count is disabled (show_child_count="0"); If show_child_count="1", but count of subpages=0, than child count is not shown;
* **child_count_template** - the template of child_count: `[pagelist_ext show_child_count="1" child_count_template="Subpages: %child_count%"]`; by default child_count_template="Subpages: %child_count%";
* **show_meta_key** - show or hide meta key: `[pagelist_ext show_meta_key="your_meta_key"]`; by default the show_meta_key is empty (show_meta_key=""); If show_meta_key is enabled, but meta_value is empty, than meta_key is not shown;
* **meta_template** - the template of meta: `[pagelist_ext show_meta_key="your_meta_key" meta_template="Meta: %meta%"]`; by default meta_template="%meta%";
* columns - for splitting list of pages into columns: `[pagelist_ext class="page-list-cols-2"]`; available classes: page-list-cols-2, page-list-cols-3, page-list-cols-4, page-list-cols-5; works in all modern browsers and IE10+;  columns are responsive and become 1 column at less than 768px;

More [info about params](http://codex.wordpress.org/Function_Reference/get_pages#Parameters) for [pagelist_ext].

== Installation ==

1. install and activate the plugin on the Plugins page
2. add shortcodes to pages: `[pagelist]`, `[subpages]`, `[siblings]`, `[topparent]`, `[pagelist_ext]`
