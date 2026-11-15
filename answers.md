# Answers

My Unix username: vardan_mkrtchyan

Public RSS feed URL: https://the.hell.am/~vardan_mkrtchyan/news.xml

Public podcast feed URL: https://the.hell.am/~vardan_mkrtchyan/podcast.xml

RSS reader and operating system used: Feeder on Android

Podcast player and operating system used: AntennaPod on Android

## RSS

1. Where did you find the first and second `<item>` elements in `news.xml`?

Both `<item>` elements are inside the `<channel>` element, after the channel information (`<title>`, `<link>`, `<description>`, `<language>`). `make_news.py` writes the newest post first, so the second post ("vardan_mkrtchyan: second post, the feed works", GUID `news-item-2`) is the first `<item>`, and my first post ("vardan_mkrtchyan: my first RSS post", GUID `news-item-1`) is the last `<item>` in the channel.

2. What is `<guid>` for? What happens if an old GUID changes?

`<guid>` is a unique identifier for an entry. The feed reader remembers the GUIDs it has already seen, so on every fetch it can tell which items are new and which ones it already has, even if their title or text changes. If the GUID of an old entry changes, the reader thinks it is a brand-new entry: the old post shows up again as a new, unread duplicate (and the old copy may stay in the list as well).

3. What did you observe after refreshing the feed reader?

After I ran `make_news.py` again and pulled to refresh in Feeder, the second post appeared at the top of the list, above the first post. The first post stayed there once and was not duplicated, because its GUID did not change. I did not have to subscribe again or notify anyone: the app just fetched the XML again and noticed the new item.

## Podcast

4. What is the difference between an ordinary RSS item and a podcast RSS item?

5. What is the value of `length` in your first `<enclosure>`? What does it measure?

6. What changed in the XML after you added the second episode?

7. Did you hear both waves in your podcast app? How are the sounds different?

## Screenshots

![RSS app](screenshots/rss.jpg)
