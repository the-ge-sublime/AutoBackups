AutoBackups
======================

Sublime Text 3 Auto backups plugin

AutoBackups is a Sublime Text 3 plugin, which automatically save a backup copy every time you save or open (if backup file not exists) a file. (Like DreamWeaver.. No, better than DreamWeaver)

When you edit text files (scripts, prose, whatever) you often find yourself wishing for an last version. Ever accidentally deleted a chunk from an important configuration file, or wished you could roll back a document a few hours? This plugin takes a copy of file you open/save and copies it into a backup directory structure, ensuring that you never lose an old version of a file. If enabled setting backup_per_day backups will be saved for each day. If enabled setting backup_per_time backups will be saved for each save.

### Configuration

To change plugin configuration, access the plugin's settings in `Preferences->Package Settings->AutoBackups`.

Configuration options:
```js
{
  // Don't make changes to this file directly as they can get wiped out when the
  // plugin is updated. Instead transfer what you need to the 'Settings - User' file.

  // The directory where we'll keep our backups; defaults to
  //"backup_dir": "C:/SublimeTextBackups",
  "backup_dir": "~/.SublimeText",

  // If true, saves a backup copy any time a file is opened (if backup file not exists)
  "backup_on_open_file": true,

  // If true, backups saved per day, in separate folders,
  // e.g. C:/SublimeTextBackups/2013-05-23/myfile.php
  "backup_per_day": true,

  // If set, backups saved per second. possible values: false, "folder" or "file"
  // false - disabled backup per second
  // "folder" -> D:/Sublime Text Backups/2013-05-23/095034/myfile.php
  // "file"   -> D:/Sublime Text Backups/2013-05-23/myfile_095034.php
  // to use this feature, you must have enabled backup_per_day setting
  "backup_per_time": "file",

  // If set, changes the filename using the following building blocks:
  //     tag i.e. "auto-save"
  //     name i.e. "myfile"
  //     date i.e. "2013-05-23"
  //     time i.e. "095034"
  //     ext i.e. "php"
  // format examples:
  //     "%name%%ext%"
  //     "%name%.%tag%%ext%"
  //     "%name%_%date%-%time%%ext%"
  //     "%tag%_%date%-%time%.%name%%ext%"
  // notice the dot in the examples, the extension includes the preceding dot
  // if None or false won't change the name
  "backup_name_mode":"%name%_%date%-%time%%ext%",

  // Files larger than this many bytes won't be backed up.
  "max_backup_file_size_bytes": 262144, // = 256 KB

  // Files older than X days will be deleted. If 0 - auto delete disabled
  "delete_old_backups": 0, // days to delete

  // ignore files/folders which match regexes
  "ignore_regexes": [
    // VCS folders
    "/\\.svn/", "/\\.hg/", "/\\.git/", "/\\.bzr/",
    // binary extensions
    "\\.(jpg|JPG|jpeg|JPEG|pjpeg|PJPEG|gif|GIF|png|PNG|apng|APNG|bmp|BMP|mp3|MP3|mid|MID|wav|WAV|au|AU|mp4|MP4|3gp|3GP|avi|AVI|wmv|WMV|mpeg|MPEG|mpg|MPG|mkv|MKV|swf|SWF|flv|FLV|zip|ZIP|rar|RAR|tar|TAR|tgz|TGZ|gz|GZ|bz2?|BZ2?|pdf|PDF|docx?|DOCX?|xlsx?|XLSX?|pptx?|PPTX?|rtf|RTF|psd|PSD|cdr|CDR|fla|FLA|exe|EXE)$"
  ],

  // If true, backup file opened in same line as cursor in original file
  "open_in_same_line": true,

  // If true, show backup previews (only in ST3)
  "show_previews": true
}
```


## Installation

**Without Git:** Download the latest source from [GitHub](https://github.com/the-ge/AutoBackups) and copy the AutoBackups folder to your Sublime Text "Packages" directory.

**With Git:** Clone the repository in your Sublime Text "Packages" directory:

```bash
git clone https://github.com/the-ge/AutoBackups.git AutoBackups
```

The "Packages" directory is located at:

 - OS X:
   - ST3 `~/Library/Application Support/Sublime Text 3/Packages/`
 - Linux:
   - ST3 `~/.config/sublime-text-3/Packages/`
 - Windows:
   - ST3 `%APPDATA%/Sublime Text 3/Packages/`

To see if plugin working, open the console with the `View->Show Console` menu item. When you save a file, you should see a line like this, indicating that the file has been backed up:

```
Backup saved to: D:/Sublime Text Backups/2013-05-23/myfile_095034.php
```

## Backup size considerations

To prevent your backup folder from growing too large, check out the `max_backup_file_size_bytes` and `delete_old_backups` setting in `Preferences->Package Settings->AutoBackups`.

## Keybindings

To open current file backup, use cmd+alt+b keybinding, or in quick panel type AutoBackup: Open file backup


## Contributing

Anyone and everyone is welcome to contribute. Please take a moment to review the [CONTRIBUTING.md](CONTRIBUTING.md) guidelines for information.


## Credits

Credit list in [CREDITS](CREDITS)

This code is available on [Github][0]. Pull requests are welcome.

Created by [Avtandil Kikabidze][2], modified by [The G][3].


## License

[MIT License](LICENSE)


 [0]: https://github.com/akalongman/sublimetext-autobackups
 [1]: https://packagecontrol.io/installation
 [2]: mailto:akalongman@gmail.com
 [3]: mailto:the.ge@pm.me
