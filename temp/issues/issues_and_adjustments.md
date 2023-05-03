# 2023-03-17

- [x] ~~Pressing Live Code should just make the buttons of the cell appear. This should not run the cells.~~

	> Implemented.

- [ ] About the buttons, wouldn’t it be better to have the following buttons in each cell:

	1. Run: run the cell
	2. Clear: clear the result of the cell
	3. Restart & Clear all: Restart the Kernel and clear of the cells
	4. Restart & Run all: Restart the Kernel and run all the cells
	
	
	> I didn't find an easy solution for this, but I'll keep searching to see if it's possible to implement this.

- [x] ~~If you manage to make Live Code work, there is no need for Binder, so I would remove that from the rocket menu~~

	> Behind the scenes Binder is needed to run the live code. I'll see if it's possible to hide Binder button.

- [x] ~~PS. Could it be a good idea having a small project with just chapter 1 and test how Live Code works on that? Once this works fine, you can add more chapters.~~

	> Once the live code now is working for all the chapters, I think there's no need for this anymore.

# 2023-04-01

- [x] ~~Some minor edits to the front page. See attached [2023-04-01_comments1.pdf]().~~

	> Done.

- [x] ~~The cell example froze after pressing Run, see attached. Using Safari 16.3 on a Mac [2023-04-01_screenshot_1247.png]()~~

	> Sometimes the kernel starts almost immediately, sometimes it takes a long time or even doesn't start at all. I don't know how to fix that yet. Still searching...

- [x] ~~The same happened in Chrome. I think the cell is unable to connect the kernel~~

	> See comments above.

- [x] ~~And Binder is also struggling to start~~

	> See comments above.

# 2023-04-03

- [x] ~~I’ll try again but when I tried I waited a lot… 10 minutes or so… My impression was that the cell was stucked…~~

	> See comments above.

# 2023-04-17

- [x] ~~I’ll try again the Book and see how it works. In any case, we should have a note saying something like these:~~

	~~*The cells in this notebook are run via Binder. Sometimes it can take long time for the kernel to start, and other times it can be quite fast. We have not figured out why this is the case, but it must be related with the installation of dependencies by Binder. We are working on it. In the meantime, be patient.*~~
	
	> Done.

- [ ] Chapter 2 with PyGMT sounds fantastic. As I said, this chapter was written by a colleague who is more interested in GIS. Yes, we can refer to the tutorials instead for the reference systems and datums sections.

	> Unfortunately porting Chapter 2 to `PyGMT` is proving to be more difficult than I anticipated. On Windows machines `PyGMT` is raising the error:*
		```
		GMTCLibNotFoundError: Error loading GMT shared library at 'libgmt.so'.
		libgmt.so: cannot open shared object file: No such file or directory
		```
	> This does not occur with mac machines. There is a workaround for this recommended by the PyGMT development team (see "Finding the GMT shared library" at https://www.pygmt.org/latest/install.html), but I think maybe this could end up complicating things too much for users. Perhaps we need to think of another alternative to `cartopy`/`PyGMT`. In the meantime, perhaps it's better to temporarily remove the sections that need `cartopy` from chapter 2 until this issue is resolved?

# 2023-04-21

- [x] ~~I tried the Jupyter book again and the Live Code option. You are right, sometimes the kernel does not start and sometimes it works perfectly. It is very fun when it works.~~

	> Great!

- [X] ~~I’ll look at the book and send comments. Attached are comments for the cover page (I believe I sent you this before) [2023-04-21_comments1.pdf]()~~

	> Yes, you sent this before. The suggestions were implemented.

- [x] ~~Here are the comments for chapter 1 [2023-04-21_comments2.pdf](). Live code is working fine, with minor glitches. This is very fun :)~~
	
	~~*Comment: run works well. restart and restart & run all don’t. restart does not clean the results, it should since it restarts the kernel. restart & run all does not do anything if called from an early cell. It should restart the kernel and run all the cells. In my opinion it would be less problematic to remove these two buttons.*~~
	
	> I think this all has to do with Jupyter Book/Thebe/Binder internals, and probably it isn't easily implemented. I can search to see if it is possible to implement at least some of these suggestions.
	
	~~*Could you include this file [[mylib.py]()] in the source/notebooks directory? Like in the compGeo repository.*~~
	
	> I think only if the user downloads the notebook and runs it directly from his/her computer. See the following comments.
	
	~~*So here it seems mylib.py is not  in the source/notebooks directory. Could you look at that?*~~
	
	> To bypass this issue, I created the `mylib.py` file and placed it in the same folder as the chapter's notebook.
	
	~~*Remove these two lines to avoid all the errors below*~~
	
	> Done.

- [ ] Here are comments for chapter 3. There were more issues here and I think this looks worse than a previous version. Am I looking at an older version? I updated to the latest version of the CompGeoTemp repository [2023-04-21_comments3.pdf]()

	~~*Something happened here and: 1. Figures links are broken. 2. Multilines figure captions are not left justified.*~~
	
	> 1. Broken links have been fixed; 2. I searched and didn't find how to implement left justification.
	
	*This gives an error [`from compgeo.zero_twopi import zero_twopi` under **The pole to the plane** subsection]*
	
	> That's odd. For me is working. Please, run again and see if it's working.
	
	~~*Remove this rectangle*~~
	
	> Fixed.
	
	*This throws an error [`from compgeo.zero_twopi import zero_twopi` under **Stereonets** subsection]*
	
	> Same as above. Please, run again and see if it's working.

	*This throws an error [`from compgeo.zero_twopi import zero_twopi` under **Plotting lines and poles in a stereonet** subsection]*
	
	> Same as above. Please, run again and see if it's working.

- [x] ~~I’ll stop reviewing here because it seems the same problems (e.g. broken figures links) occur in the next chapters~~

	> Solved. Broken links have been fixed.
