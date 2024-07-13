# Netflix's Simian Army

When you're distributing databases across a whole host of nodes, you have to prepare for the worst. Sometimes the worst is the new intern who pushes [hello world to production](https://www.reddit.com/r/webdev/comments/1cae7j5/netflix_left_their_test_page_in_production/) and sometimes it's an army of "monkeys" that go around purposefully overloading servers with requests or taking down whole geographical regions.

Anyways, it's quite cool that they have a whole suite of tools that is constantly running to stress test their system, so that when the worst really does come, our televisions will still be streaming Netflix originals.

[source](https://netflixtechblog.com/the-netflix-simian-army-16e57fbab116)