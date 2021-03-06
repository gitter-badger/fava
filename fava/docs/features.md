---
title: Fava's features
---

This is an overview of some of the more advanced features that Fava has to offer.

## Keyboard Shortcuts

Fava comes with keyboard shortcuts: Press <kbd>?</kbd> on any page to show an
overview.

## Filters

There are four filters available in Fava:

- **Time**: Filter entries by their date. This filter does some free-text
  recognition, which means you can enter terms like `This Month`, `2015-03`,
  `March 2015`, `Mar 2015`, `Last Year`, `Aug Last Year`, `2010-10 - 2014` or
  `Year to Date`
- **Tags**: Filter entries to the ones having the tags selected. This filter is
  inclusive, meaning that if you select multiple tags entries with any of those
  tags will be filtered.
- **Account**: Filter entries by account, matching any entry where this account
  is part of.
- **Payee**: Filter entries by payee. This filter is, like the *Tags*-filter,
  inclusive.

If you select multiple filters (like *Tags* and *Time*), the subset of entries
matching both filters will be selected.

## Up-to-date indicators

Fava offers colored indicators that can help you keep your accounts up-to-date.
They are shown everywhere by default, but only enabled for accounts that have
the metadata `fava-uptodate-indication: "True"` set on their Open directive.
The colors have the following meaning:

- green: The last entry for this account is a balance check that passed.
- red: The last entry is a balance check that failed.
- yellow: The last entry is not a balance check.
- gray: The account has not been updated in a while, as set by the
  `uptodate-indicator-grey-lookback-days` configuration variable.

## Displaying only relevant accounts

To help display only the most relevant subset of accounts when managing a large number
or a deep hierarchy of accounts, Fava offers several configuration variables listed
below. The first three are self-explanatory:

- `show-closed-accounts`
- `show-accounts-with-zero-balance`
- `show-accounts-with-zero-transactions`
- `collapse-accounts` takes a list of accounts that are collapsed in the initial tree view

## Opening an external editor

Fava can open up your source file in your favorite editor directly from the web
interface using the `use-external-editor` configuration variable through the
`beancount://` URL handler. See the [beancount
urlscheme](https://github.com/aumayr/beancount_urlscheme) project for
pre-configured URL handlers for OS X and Cygwin.

## Query Export

By default, Fava only supports export to `csv` for query results. For support
of `xls`, `xlsx` and `ods`, install Fava with the `excel` feature:

    pip3 install fava[excel]

## Multiple Beancount files

When you start Fava specifying multiple Beancount files, you can click the
Beancount file name on the top left to switch between the files.

## Custom links in the sidebar

If you regularly use certain views in Fava with different filters, etc., you can
put these permalinks in the sidebar. Custom links can be put in the beancount
file, utilizing the `custom` directive:

    2016-05-04 custom "fava-sidebar-link" "Income 2014" "/income_statement?time=2014"

`"fava-sidebar-link"` specifies that this directive is for a custom sidebar
link, followed by the title to display in the sidebar (`"Income 2014"` in this
example), and finally the URL to link to. The URL can be relative, like in the
example above, or absolute, even linking to an external site.

## Language

You can change the language of the interface by specifying the `language` setting.
Currently Fava supports English (`en`) and German (`de`).

If no setting is specified, Fava tries to guess the language from your browser
settings.
