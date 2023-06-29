# Making clips with ffmpeg

**tl;dr** `ffmpeg -y -ss {start} -i in.mp4 -t {dur} -c copy out.mp4`

So, ffmpeg is a finnicky tool. If you want to take a snippet out of a video, an easy way to do this might just be `ffmpeg -y -i in.mp4 -ss {start} -t {dur} -async 1 out.mp4`, but this is actually **excruciatingly slow**.

It turns out that *where* you put the `-ss` flag matters a lot, and that putting it *in front of* the `-i` will drastically speed up the copying. I think there's a tradeoff between speed and accuracy of putting it before or after `-i`, but putting it before seems to work well enough for me. There's also the issue of reencoding the video which is computationally expensive, so you'll want to include `-c copy`.

All in all, the final code to do this is next to the tldr.