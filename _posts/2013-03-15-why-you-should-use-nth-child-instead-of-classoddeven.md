---
id: 101
title: 'Why you should use nth-child instead of class=&#8221;odd|even&#8221;'
date: '2013-03-15T21:21:17-05:00'
author: David
layout: post
guid: 'http://davidwritescode.com/blog/?p=101'
permalink: /why-you-should-use-nth-child-instead-of-classoddeven/
dsq_thread_id:
    - '1140781351'
amazonS3_cache:
    - 'a:8:{s:95:"//davidlwatsonjr.com/blog/wp-content/uploads/2013/03/davidlwatsonjr-–-Users-at-Last.fm_-1.png";a:2:{s:2:"id";i:243;s:11:"source_type";s:13:"media-library";}s:104:"//davidlwatsonjr.com/blog/wp-content/uploads/2013/03/davidlwatsonjr-–-Users-at-Last.fm_-1-1024x531.png";a:2:{s:2:"id";i:243;s:11:"source_type";s:13:"media-library";}s:126:"//david-writes-code.storage.googleapis.com/blog/wp-content/uploads/2013/03/21130800/davidlwatsonjr-–-Users-at-Last.fm_-1.png";a:2:{s:2:"id";i:243;s:11:"source_type";s:13:"media-library";}s:135:"//david-writes-code.storage.googleapis.com/blog/wp-content/uploads/2013/03/21130800/davidlwatsonjr-–-Users-at-Last.fm_-1-1024x531.png";a:2:{s:2:"id";i:243;s:11:"source_type";s:13:"media-library";}s:104:"//davidlwatsonjr.com/blog/wp-content/uploads/2013/03/davidlwatsonjr-–-Users-at-Last.fm-nth-child-1.png";a:2:{s:2:"id";i:245;s:11:"source_type";s:13:"media-library";}s:113:"//davidlwatsonjr.com/blog/wp-content/uploads/2013/03/davidlwatsonjr-–-Users-at-Last.fm-nth-child-1-1024x557.png";a:2:{s:2:"id";i:245;s:11:"source_type";s:13:"media-library";}s:135:"//david-writes-code.storage.googleapis.com/blog/wp-content/uploads/2013/03/21130944/davidlwatsonjr-–-Users-at-Last.fm-nth-child-1.png";a:2:{s:2:"id";i:245;s:11:"source_type";s:13:"media-library";}s:144:"//david-writes-code.storage.googleapis.com/blog/wp-content/uploads/2013/03/21130944/davidlwatsonjr-–-Users-at-Last.fm-nth-child-1-1024x557.png";a:2:{s:2:"id";i:245;s:11:"source_type";s:13:"media-library";}}'
categories:
    - CSS
tags:
    - css
    - last.fm
---

Take a gander at this:

[![My last.fm track list after deleting a few songs.](https://david-writes-code.storage.googleapis.com/blog/wp-content/uploads/2013/03/21130800/davidlwatsonjr-%E2%80%93-Users-at-Last.fm_-1-1024x531.png)](https://david-writes-code.storage.googleapis.com/blog/wp-content/uploads/2013/03/21130800/davidlwatsonjr-%E2%80%93-Users-at-Last.fm_-1.png)

That’s my track listing on last.fm after I’ve deleted a few duplicates (thank you, last.fm Android app).

Notice anything funny? Yeah. How about those background colors.

See, last.fm slaps every other row with an “odd” class. They then target that class to alternate background colors for every other row.

But what if they used some nth-child magic instead? Why, this:

[![My last.fm track list after deleting a few songs but using nth-child selection.](https://david-writes-code.storage.googleapis.com/blog/wp-content/uploads/2013/03/21130944/davidlwatsonjr-%E2%80%93-Users-at-Last.fm-nth-child-1-1024x557.png)](https://david-writes-code.storage.googleapis.com/blog/wp-content/uploads/2013/03/21130944/davidlwatsonjr-%E2%80%93-Users-at-Last.fm-nth-child-1.png)

I took 6.9 seconds and changed their selector from

```
table.tracklist tr.odd
```

to

```
table.tracklist tr:nth-child(odd)
```

[Can I use…](http://caniuse.com/#search=nth-child "Can I use...") says I can use this selector on any modern browser (as long as we exclude IE 8 from modern, which should be the case).

So, last.fm, get on it.