A command line tool for accessing the EteSync journal and collections (e.g. Calendars)

# Intro

This will at some point become a fully fledge tool, though at the moment it's quite raw.

Also, it's important to know that while the derived password and auth token are
cached in an encrypted file, the contents of your journal, are not! The local etesync
cache is located at: ```~/.etesync/data.db```.

Please let us know what you think should be done next, and patches are more than welcome!

# Installation

There's currently no installation process, just get the ```etesync-cli``` script from
this repo, and run it.

# Usage

Help:

```etesync-cli -h```

Add user:

```etesync-cli user add me@etesync.com```

Viewing your data:

Sync (sync is not automatic!)

```
$ etesync-cli sync me@etesync.com
```

View the list of collections:

```
$ etesync-cli list me@etesync.com
# Address Books
        Default (0530a37fd91426293759cea8aa8d330f9945f323254236d1472e94aeef6a6e8f)

# Calendars
        Default (b71504d4fef88e685472bb7a77f10c338d7e6bef9041994e3809e7622727f5a3)
        Reminders (666d05611f46b820831ef75d6e6f58098272c12b793e9b33a8476362b3704e3f)

$ etesync-cli list me@etesync.com 666d0561
Journal items: 4
Collection items: 1

# Items
 VCALENDAR
    VERSION: 2.0
    PRODID: +//IDN bitfire.at//ical4android
    VEVENT
       DTSTAMP: 2017-03-24 16:50:21+00:00
       UID: 4d7be429-e311-4da9-bc34-87c4a01dc37f
       DTSTART: 2017-03-25 16:00:00+00:00
       params for  DTSTART:
          X-VOBJ-ORIGINAL-TZID ['Europe/London']
       DTEND: 2017-03-25 17:00:00+00:00
       params for  DTEND:
          X-VOBJ-ORIGINAL-TZID ['Europe/London']
       SUMMARY: Go to supermarket
       STATUS: CONFIRMED
    VTIMEZONE
    TZID: <TZID{}Europe/London>
```
