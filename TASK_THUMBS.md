# Task: strict QC of 25 YouTube thumbnails

`thumbs/epNN.jpg` (1280x720) are the new thumbnails of the long episodes; `thumbs/titles.json` has each video title, the big thumbnail text and a summary of the episode. `overview/epNN.jpg` = one frame per minute of the episode (label h:mm) if you need a better frame.

For EVERY thumbnail (Read each image) check and report:
1. Any inventory, chest, crafting or other menu, chat text, debug text, item tooltip visible? (instant FAIL)
2. Is the main subject (house, windmill, bridge, boat...) covered or cut by the big text (bottom-left) or by the small pill (top-right)? Is the subject even readable at small size?
3. Does the big text match what the picture shows (e.g. "FISHING IN THE RAIN" must show rain and fishing; "HORSES COME HOME" should show horses)? Does it match the title?
4. Would it make a stranger click (light, colour, one clear subject)?
Verdict per thumbnail: OK / FIX. For FIX give concrete instructions: a better frame time (h:mm from the overview, or "keep frame"), text position (bl = bottom-left, tl = top-left, br = bottom-right), horizontal crop centre 0.0-1.0 to keep the subject clear of the text, and/or new text (2-4 words, must match the picture and the title).
Final reply: a JSON {"ep01": {"verdict": "OK|FIX", "problems": "...", "frame": "keep|h:mm", "pos": "bl|tl|br", "x": 0.5, "text": "LINE1|LINE2"}, ...} and nothing else.
