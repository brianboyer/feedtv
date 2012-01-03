Getting started:

* Put your Roku in developer mode: Home Home Home Up Up Left Right Left Right Left
* The build script will make a zip file and push it out to the Roku. You'll probably need to change the IP address.
* Reference: http://c1807832.r32.cf0.rackcdn.com/ComponentReference_v41.pdf
* Forum: http://forums.roku.com/viewforum.php?f=34
* SDK and stuff: http://www.roku.com/developer

What's the point?

The user experience of on-demand video is miserable. Instead of making ten choices before you can actually watch something, can't I just watch the TV? This little project is my attempt to invert the UI, putting streaming content first, and choices second.

Features:

* X instant play at beginning
* X plays contunuously
* X go to next/previous video
* X back out to the list of videos you're watching
* X stores what you've recently watched (and skipped) so as to not repeat (watched vids are still on the list) -- uses registry
* PIP? look at video list w/o stopping video
* live video -- when it's live, we stream that at the front of the list
* mark a video as a favorite to watch later -- uses registry
* show movie info, including a short link for web viewing
* show instructions
* pre-buffer next feed, for smooth playback (load it up, pause when isStreamStarted() event fires?)

Buttons:

back   -- backs out to list (back to video? back to home screen?)
up     -- same as back??  (navigates videos in list mode)
left   -- goes to previous video (navigates videos in list mode)
right  -- goes to next video (navigates videos in list mode)
down   -- ?? (navigates videos in list mode)
replay -- default
ok     -- marks a video as watched and skips ahead (selects a video when in list mode)
star   -- ?? (marks this video as a favorite for later?)
<<     -- seek backwards
>      -- play/pause
>>     -- seek forwards

Content format:

JSON file sets up the whole shebang. you've still got to set up your own manifest and stuff, but this is the file that you'll periodically publish so that the system has the latest videos, etc.

{
	categories: [
		{
			name: 'cat 1',
			videos: [
				{video1}.
				{video2}
				{etc...}
			]
		},
		{
			name: 'cat 2',
			videos: [
				{video1}.
				{video2}
				{etc...}
			]
		}
	]
}

OR... we use MRSS, like currently configured

