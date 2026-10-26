# Brief: pick moments for YouTube Shorts from Minecraft longplay footage

Context: Ivan's old channel "No Talk Minecraft" (English, cozy no-commentary Minecraft longplays, 1.21.8 with shaders, 2025). We are cutting vertical 9:16 Shorts (15-40 s) from the original footage. The footage is first-person survival gameplay with a HUD. The vertical crop takes the CENTRE ~32% of the width of the 16:9 frame (it can be shifted left/right), full height.

You get contact sheets `<ep>_cand_NN.jpg` in `cand/` in this repo. Each row = one candidate window (a stretch with no inventory screen and moderate camera motion): left label = window id, start (min:sec in the episode), duration, motion (mean) and j (95th percentile motion, lower = smoother). 4 frames per row at 10/37/63/90 % of the window. The matching `<ep>_cand.json` has exact start/end seconds per id.

Look at EVERY sheet of your episodes (use the Read tool on the jpg). Pick only moments that would make a stranger stop scrolling: beautiful light (sunset, golden hour, dusk with lanterns, night with warm windows, fireflies), water and boats, cherry blossoms, rain, a finished cozy build seen from outside or a cozy interior, a walk along a lantern-lit path, a village, animals. Reject: inventory/chest/crafting screens (the detector misses some), staring at dirt/stone/walls up close, mining tunnels, chaotic camera, dark unreadable frames, menus, half-built mess (unless it is clearly a build in progress worth a before/after).

Also note any recurring BUILD or PLACE (the base, a windmill, a stable, a village, a house) and how it looks at that point, so we can later make "progress over time" shorts across episodes.

Write your result as JSON to `picks/picks_<episodes>.json` (e.g. `picks/picks_ep16-ep19.json`):
{"episode_notes": {"<ep>": "one line: what happens / what is built in this episode"},
 "picks": [{"id": "ep24-w026", "start": 1077.8, "end": 1105.8, "use_from": 1080.0, "use_to": 1100.0,
            "category": "boat|scenic|village|path_walk|build_reveal|interior|rain|night|sunset|animals|build_progress",
            "beauty": 1-5, "smooth_guess": 1-5, "x_hint": 0.5,
            "what": "short description of what is on screen", "caption_idea": "a short hook text for the Short"}],
 "builds": [{"name": "windmill", "ep": "ep24", "t": 1300, "state": "frame only|half|finished", "note": "..."}]}
`use_from/use_to` = the best sub-range in episode seconds (interpolate between the 4 frames). `x_hint` = where the interesting subject sits horizontally (0 = left edge, 0.5 = centre, 1 = right), so the vertical crop can follow it. Keep only beauty >= 3; be strict, quality over quantity, typically 4-10 picks per episode. In the final message just reply with the number of picks per episode and the 3 best ids overall.
