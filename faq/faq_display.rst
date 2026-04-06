.. MusicBrainz Picard Documentation Project

Display
=======

:index:`How do I change the fonts size or font? <change font size>`
--------------------------------------------------------------------

Picard is a Qt application, so whatever works for other Qt applications should work for Picard.

**Windows**

   This is generally managed through the Windows display settings, where you can change the size of text, apps and other items. This should work for Picard as well as other applications.

   Additional information can be found in the Windows article, "`Make text and apps bigger <https://support.microsoft.com/en-us/windows/make-text-and-apps-bigger-c3095a80-6edd-4779-9282-623c4d721d64>`_".

   An alternate approach is to set the environment variable ``QT_SCALE_FACTOR`` to scale fonts for Qt applications globally or for specific applications. This can be useful on 4k monitors. More information can be found in the reddit post, "`Need help with app interface scaling in Windows 11 <https://www.reddit.com/r/qBittorrent/comments/zqafe9/comment/j1i0z0v>`_".


**macOS**

   This is generally managed through the System Preferences, where you can change the display settings to adjust the size of text and other items. This should work for Picard as well as other applications.

   Additional information can be found in the Apple article, "`Increase font size and icons on Mac <https://support.apple.com/en-ca/guide/mac-help/mchld786f2cd/mac>`_" or the iDownloadBlog article, "`How to adjust the text size of specific apps on Mac <https://www.idownloadblog.com/2023/06/28/how-to-adjust-text-size-apps-mac/>`_".


**Linux**

   Two ways to change the size/scaling are:

   1. Desktop Settings

      |  The usual default way to change the scaling is to rely on the settings of the desktop environment, e.g. on GNOME the scaling set when configuring the screens. This usually works, and should be the first approach to take.

   2. Environment Settings

      |  Setting the environment variable ``QT_SCALE_FACTOR`` will scale fonts for Qt applications. This can be useful on 4k monitors. From a terminal, you can then run ``QT_SCALE_FACTOR=2.0 picard`` to start Picard, or create an alias in your shell, or set the variable in your shell to affect all Qt applications.

   To change both the size/scaling and the font, use `qt6ct <https://github.com/trialuser02/qt6ct>`_ to set the new font and/or size. Note that these changes will apply to all Qt applications, not just Picard.

.. seealso::

   Additional information regarding high DPI scaling on all platforms can be found in "`The official documentation on high DPI <https://doc.qt.io/qt-6/highdpi.html>`_".
