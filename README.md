
LaChronologie (module pour Omeka S by Ahcene BELMERABET)
=============================

LINK GITHUB "https://github.com/ahceneBelmerabet/LaChronologie"

La chronologie permet aux créateurs de sites Web d'intégrer des chronologies interactives dans leurs sites.



 Installation
 ------------

 Uncompress files in the module directory and rename module folder `Timeline`.

 Then install it like any other Omeka module and follow the config instructions.

 Note: If Omeka is https, if external assets are used, and if the Simile library
 is used, the library will not load on recent browsers, because the online
 library contains an url with unsecure http. In that case, you need to set the
 option "Use Internal library for Simile".

 Choose which fields you want the module to use on the timeline by default.

 * Item Title: The field you would like displayed for the item’s title in its
   information bubble. The default is `dcterms:title`.
 * Item Description: The field you would like displayed for the item’s
   description in its information bubble. The default is `dcterms:description`.
 * Item Date: The field you would like to use for item dates on the timeline.
   The default is `dcterms:date`.
 * Item Date End: The field you would like to use for item end dates on the
   timeline. It is useless if dates are ranges (see below) or if you don’t have
   end date.
 * Render Year: Date entered as a single number, like `1066`, can be skipped,
   plotted as a single event or marked as a full year.
 * Center Date: The date that is displayed by the viewer when loaded. It can
   be any date with the format `YYYY-MM-DD`. An empty string means now, a
   `0000-00-00` the earliest date and `9999-99-99` the latest date.
 * Viewer: The raw json parameters for the viewer, for example to display only
   one row, or to change the scale.

 All these parameters can be customized for each timeline.


 Usage
 -----

 Once enabled, the module adds a new block for site pages. Simply select it and
 config it (the item pool and eventually the options).


 ### Dates for Items

 Timeline will attempt to convert the value for a date string into an [ISO 8601]
 date format. Some example date values you can use:

   * `January 1, 2012`
   * `2012-01-01`
   * `1 Jan 2012`
   * `2012-12-15`

 To denote spans of time, separate the start and end date with a `/`:

   * `January 1, 2012/February 1, 2012`

 A common format is managed too:

   * `1939-1945`

 It must be `1939/1945` to be compatible with the standard ISO 8601.

 Timeline handles dates with years shorter than 4 digits. For these you may need
 to pad the years with enough zeros to make them have four digits. For example,
 `476` should be written `0476`.

 Also, you can enter in years before common era by putting a negative sign before
 the year. If the date has less than four digits, you’ll also need to add extra
 zeros.

 So here are some more examples of dates.

   * `0200-01-01`
   * `0002-01-01`
   * `-0002-01-01`
   * `-2013-01-01`

 When a date is a single number, like `1066`, a parameter in the config page
 allows to choose its rendering:

   * skip the record (default)
   * 1st January
   * 1st July
   * full year (range period)

 This parameter applies with a range of dates too, for example `1939/1945`.

 In all cases, it’s recommended to follow the standard [ISO 8601] as much as
 possible and to be as specific as possible.

 ### Modifying the block template for Timeline

 To modify the block template, copy it in your theme (file `view/common/block-layout/timeline.phtml`).

 ### Modifying the viewer

 The template file used to load the timeline is `asset/js/timeline.js`.

 You can copy it in your `themes/my_theme/asset/js` folder to customize it. The
 same for the default css. See the main [wiki], an [example of use] with Neatline
 for Omeka Classic, and the [examples] of customization on the wiki.


 Warning
 -------

 Use it at your own risk.

 It’s always recommended to backup your files and your databases and to check
 your archives regularly so you can roll back if needed.


 Troubleshooting
 ---------------

 See online issues on the [module issues] page on GitHub.

 Contacts
 --------

 * BELMERABET-Ahcene (see [BELMERABET-Ahcene] on GitHub)

