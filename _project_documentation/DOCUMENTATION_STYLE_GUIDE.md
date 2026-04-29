# Documentation Style Guide

The following sections are intended to provide some guidance when preparing or modifying the Picard Documentation source files.


## File Type

The documentation preparation and generation is handled by [Sphinx](https://www.sphinx-doc.org). Although Sphinx can process both [RestructuredText](https://www.sphinx-doc.org/en/master/usage/restructuredtext/index.html) (\*.rst) and Markdown (\*.md) input files, the decision was made to use RestructuredText files for this project. The primary reason for this decision was the superior handling of links and bookmarks provided by RestructuredText.

Submitted pull requests should provide new content or changes in `*.rst` files. If you are not familiar with RestructuredText and are unable to provide the submission in this format, please contact us for assistance in preparing the changes in the appropriate format.


## General Style Considerations

Note that the original language for the documentation is English (typically US English). Some items such as case selection and spacing may differ for translations into other languages and locales. Please check the spelling and grammar before submitting your changes.

The following items indicate the preferred style elements for the base language documentation.

### Long lines

When content includes a lengthy paragraph, the preference is to provide this as a single long line rather than multiple shorter lines manually wrapped. For example:

    This is an example of a
    long paragraph that has
    been word wrapped by
    splitting the line into
    multiple short lines in
    the file. This is not
    the preferred method
    for submitting the file.

The preferred method would be to provide this as a single long line as:

    This is an example...submitting the file.

Note that most editors allow you to enable soft line breaks, allowing you to enter long lines that will be displayed as wrapped within the editor but will be saved as a single line without the line breaks.

### Spacing between sentences

The preference is to provide a single space between sentences. For example:

    This is the preferred. One space.
    This is not the way to do it.  Two spaces.
    This is also not the way to do it.No spaces.

### Case Selection

First and second level section titles should be entered in ***Title Case***. The exception to this is items in the Frequently Asked Questions (FAQ) section that are shown as questions, which should be entered in ***Sentence case***.

Third and subsequent level titles should be entered in ***Sentence case***.


## RestructuredText Considerations

The following are considerations and preferences related to RestructuredText roles, directives, references and other elements.

### Header levels

The general convention for identifying header levels (by underlining the header) is to use the following characters for the underline:

- Level 1 (Top Level): `=` (equals sign)
- Level 2: `-` (dash / minus sign)
- Level 3: `+` (plus sign)
- Level 4: `'` (apostrophe)

For example:

    Top Level Heading
    =================

    Second Level Heading
    --------------------

    Third level heading
    +++++++++++++++++++

    Fourth level heading
    ''''''''''''''''''''

### Link references

When links are within the site, such as those in `:doc:` roles, they should use relative references. For example:

    :doc:`correct <../about_picard/contributing>
    :doc:`incorrect </about_picard/contributing>

### Keyboard references

Keyboard references are shown using the `:kbd:` role, with each key separated by a plus sign with no surrounding spaces. For example:

    :kbd:`Ctrl+E`
    :kbd:`⌘+E`

Standard key names used include `Ctrl` (`⌘` for macOS), `Shift` (`⇧` for macOS), `F1` (`⌘+?` for macOS) through `F12`, `Alt` (`⌥` for macOS), `Ins`, `Del` (`⌘+⌫` for macOS), `Tab` and `Space`.

### Button references

Buttons can be displayed within a line of text by using the `:guilabel:` role. For example:

    Click :guilabel:`Make It So!` to save your settings.

### Menu references

References to items from the menu bar should be entered using the `:menuselection:` role. Submenu item selections can be indicated by entering the selection chain, with each menu / submenu separated by `-->`. Menu bar selections or selection chains may be enclosed in double quotes (`"`) for clarity. For example:

    Add your files using :menuselection:`"Files --> Add Files…"` or :menuselection:`"Files --> Add Folder…"`.

### Code blocks

Although RestructuredText allows identifying a code block by indenting the code following a paragraph ending with two colon characters (::), the preferred method for this documentation is to enter it as a [`code-block`](https://documatt.com/restructuredtext-reference/element/code-block.html) directive. For example:

    This type of code block definition should not be used::

       $set(album,%album%$if(%_releasecomment%, \(%_releasecomment%\)))

    The preferred method is define the code block as a directive, such as:

    .. code-block:: taggerscript

       $set(album,%album%$if(%_releasecomment%, \(%_releasecomment%\)))

### Admonitions

[Admonitions](https://documatt.com/restructuredtext-reference/admonitions.html) such as `note`, `caution`, `warning` and `seealso` can be used to emphasize specific information to the user. Care must be taken to strike a proper balance and not overuse admonitions.

### Images

The preferred format for images used in documentation pages is Portable Network Graphics (PNG). Images should not contain any spaces in the file name, and should be stored in the appropriate section's `images` directory. For example:

- Wrong: `config/my_image.png` (not in the `images` directory)
- Wrong: `config/images/my image.png` (space in the image file name)
- Right: `config/images/my_image.png`

Images should be scaled appropriately for display in the documentation page, and appropriately placed on the page. Typically images will be placed above the text describing or explaining the image, and horizontally centered. In some cases it may be more appropriate to place the image either left or right justified, with the text beside the image. Typically this would be done if the image is small or tall and narrow.

Large images should be typically scaled to 75% to 80% width (as appropriate) for the PDF pages (latex), and no scale specified for the HTML pages because they will be auto scaled to 100% width by the software. Typically a new line needs to be forced after the image for the HTML pages to avoid having the following text appear crowded immediately below the image. This is done by inserting a line containing a single vertical bar. For example:

    .. only:: not latex

    .. image:: images/options-player.png
       :align: center

    |

    .. only:: latex

    .. image:: images/options-player.png
       :width: 75%
       :align: center

### Index entries

Topics can be included with a page number reference in the generated PDF documentation by using the [`index`](https://www.sphinx-doc.org/en/master/usage/restructuredtext/directives.html#index-generating-markup) role or directive. Typically the role is used to provide references to specific portions of a paragraph rather than a whole block of text as provided by the directive. For example:

    Use :menuselection:`"Tools --> Cluster"` to group the files into album :index:`clusters <pair: cluster; lookup>`.
