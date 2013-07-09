=== Exports and Reports ===
Contributors: sc0ttkclark
Donate link: http://scottkclark.com/
Tags: exports, reports, reporting, exporting, csv, tab, xml, json
Requires at least: 3.0
Tested up to: 3.5.1
Stable tag: 0.5.3

Define custom exports / reports for users, based off of any custom MySQL SELECT query you define.

== Description ==

**THIS IS A BETA VERSION - Currently in development**

Define custom exports / reports for users, based off of any MySQL SELECT query you create. This plugin interacts with your SELECT query and does all the hard work for you: exporting, pagination, ordering, searching/filtering, and display formatting for you.

All you do is install the plugin, create your Groups, create your Reports, and hand it off to your clients. Exportable reports in CSV, TSV, XML, JSON, and custom delimiter separated formats.

== Frequently Asked Questions ==

**What are Groups?**

Groups are groupings of Reports that are given their own menu item in the "Reports" menu.

**What is a Report?**

A Report is defined by a Custom MySQL query and can be configured to display however you wish using additional field definitions. Exports can be disabled per report.

**My report isn't working**

As an admin, add &debug=1 to the end of the report URL to see the query that this plugin uses, take that query and use it in your own MySQL client or PHPMyAdmin to see if there are any errors in your own query.

== Changelog ==

= 0.5.3 =
* Fix for exporting and URL paths on Windows, props to @fantomas_bg

= 0.5.2 =
* Bug fixes, added nonces for exports

= 0.5.1 =
* Feature: Reports menu split from Reports Admin so they're two separate menus now to avoid confusion for users
* Feature: Ability to reorder Groups so you can choose the order they appear in the menu
* Feature: Ability to set a separate query for use when getting the 'total' count (for advanced / complex queries which otherwise would be a bad idea to use SQL_CALC_FOUND_ROWS for)
* Feature: Report field settings now have 'Advanced' section that can be expanded to view advanced settings, otherwise you can use the three simple settings which are 'Field Name', 'Data Type', and 'Label (optional)'
* Feature: Now when you don't enter ANY fields in the Field Settings area, the report will pick up fields directly from the query for you when you display a report
* Feature: When making a boolean data type field filterable, a new filter will appear to choose '-- Show All --', 'Yes', and/or 'No'
* Feature: If you're having trouble with a report, you can enable debug mode by adding debug=1 to the Report URL (must be Administrator)
* Fix: Date fields that are empty (0000-00-00 00:00:00) will now show 'N/A' instead
* Fix: Related fields have better handling for SQL building
* Fix: No longer using default ORDER BY when no ORDER BY is found in SQL, causing issues with tables that didn't have a field 'id' set
* Fix: Smarter WHERE and HAVING dynamic building
* Fix: Lots of PHP warnings / notice cleanups and general code tweaks to plugin and WP_Admin_UI class

= 0.4.2 =
* Feature: Added ability to set the a field's filter default value
* Feature: Added additional 'related' field type options (where/order by SQL, related ON field)
* Feature: Added 'default_none' option to DB and Report editor, which allows you to default a report to show no results until a search / filter is done, exports clicked will continue to generate the full export before search and/or filtering
* Feature: EXPORTS_REPORTS_DISABLE_MENU constant added to disable the menu from being output completely (aside from the normal exports_reports_* capabilities you can define under user roles
* Fix: Added comments to SQL Query field in Report editor to explain advanced %%TAGS%% which can be used
* Fix: Reports list now ordered by Group then Weight (same for reordering)
* Fix: Forcing version to be int instead of text when getting version from DB
* Fix: Various minor bug fixes to plugin and WP Admin UI class

= 0.3.3 =
* Bug fix for SQL (another)

= 0.3.2 =
* Bug fix for SQL
* Moved About to bottom of Menu
* Added 'Reset' option in Settings

= 0.3.1 =
* Fixed menu access

= 0.3 =
* Upgraded Admin.class.php with Bug fixes and features (better UI and filtering)
* Export data fixes on CSV / TSV to support Excel
* Redefined Date Data Type into three (Date, Date + Time, Time)
* Filter by Date
* Ability to clear entire export directory (based on logged export files)
* Daily Export Cleanup via wp_cron

= 0.2 =
* First official release to the public as a plugin

== Upgrade Notice ==

= 0.5.1 =
* Feature: Reports menu split from Reports Admin so they're two separate menus now to avoid confusion for users
* Feature: Ability to reorder Groups so you can choose the order they appear in the menu
* Feature: Ability to set a separate query for use when getting the 'total' count (for advanced / complex queries which otherwise would be a bad idea to use SQL_CALC_FOUND_ROWS for)
* Feature: Report field settings now have 'Advanced' section that can be expanded to view advanced settings, otherwise you can use the three simple settings which are 'Field Name', 'Data Type', and 'Label (optional)'
* Feature: Now when you don't enter ANY fields in the Field Settings area, the report will pick up fields directly from the query for you when you display a report
* Feature: When making a boolean data type field filterable, a new filter will appear to choose '-- Show All --', 'Yes', and/or 'No'
* Feature: If you're having trouble with a report, you can enable debug mode by adding debug=1 to the Report URL (must be Administrator)
* Fix: Date fields that are empty (0000-00-00 00:00:00) will now show 'N/A' instead
* Fix: Related fields have better handling for SQL building
* Fix: No longer using default ORDER BY when no ORDER BY is found in SQL, causing issues with tables that didn't have a field 'id' set
* Fix: Smarter WHERE and HAVING dynamic building
* Fix: Lots of PHP warnings / notice cleanups and general code tweaks to plugin and WP_Admin_UI class

= 0.4.2 =

= 0.4.2 =
* Feature: Added ability to set the a field's filter default value
* Feature: Added additional 'related' field type options (where/order by SQL, related ON field)
* Feature: Added 'default_none' option to DB and Report editor, which allows you to default a report to show no results until a search / filter is done, exports clicked will continue to generate the full export before search and/or filtering
* Feature: EXPORTS_REPORTS_DISABLE_MENU constant added to disable the menu from being output completely (aside from the normal exports_reports_* capabilities you can define under user roles
* Fix: Added comments to SQL Query field in Report editor to explain advanced %%TAGS%% which can be used
* Fix: Reports list now ordered by Group then Weight (same for reordering)
* Fix: Forcing version to be int instead of text when getting version from DB
* Fix: Various minor bug fixes to plugin and WP Admin UI class

= 0.3.3 =
* Bug fix for SQL (another)

= 0.3.2 =
* Bug fix for SQL
* Moved About to bottom of Menu
* Added 'Reset' option in Settings

= 0.3.1 =
* Fixed menu access

= 0.3 =
* Upgraded Admin.class.php with Bug fixes and features (better UI and filtering)
* Export data fixes on CSV / TSV to support Excel
* Redefined Date Data Type into three (Date, Date + Time, Time)
* Filter by Date
* Ability to clear entire export directory (based on logged export files)
* Daily Export Cleanup via wp_cron

= 0.2 =
* First official release to the public as a plugin

== Installation ==

1. Unpack the entire contents of this plugin zip file into your `wp-content/plugins/` folder locally
1. Upload to your site
1. Navigate to `wp-admin/plugins.php` on your site (your WP plugin page)
1. Activate this plugin

OR you can just install it with WordPress by going to Plugins >> Add New >> and type this plugin's name

== Official Support ==

Exports and Reports - Support Forums: http://scottkclark.com/forums/exports-and-reports/

== About the Plugin Author ==

Scott Kingsley Clark from SKC Development -- Scott specializes in WordPress and Pods CMS Framework development using PHP, MySQL, and AJAX. Scott is also a developer on the Pods CMS Framework plugin

== Features ==

= Administration =
* Create and Manage Groups
* Create and Manage Reports
* Limit which User Roles have access to a Group or Report
* Ability to clear entire export directory (based on logged export files)
* Daily Export Cleanup via wp_cron
* WP Admin UI - A class for plugins to manage data using the WordPress UI appearance

= Reporting =
* Filter by Date
* Automatic Pagination
* Show only the fields you want to show
* Pre-display modification through custom defined function per field or row

= Exporting =
* CSV - Comma-separated Values (w/ Excel support)
* TSV - Tab-separated Values (w/ Excel support)
* XML - XML 1.0 UTF-8 data
* JSON - JSON for use in Javascript and PHP5+
* Custom - Custom delimiter separated Values