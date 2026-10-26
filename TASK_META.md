# Task: content notes for the 25 long episodes

`overview/epNN.jpg` = one frame per minute of episode NN (label = h:mm of the episode), 10 frames per row. These are 85-110 min no-commentary cozy Minecraft survival longplays (1.21.8, shaders from about ep05) of ONE continuous world, episodes 01-25 in order. We are rewriting the YouTube titles/descriptions/thumbnails so every episode stands on its own (no "part N", no version number).

Look at every sheet (Read tool). Use what you already know from ep14-ep25 picks. For each episode return:
- `summary`: 2 short sentences, concrete (what is built / explored / where, weather and light highlights).
- `focus`: the one thing this episode is about, 2-5 words (e.g. "building a windmill", "first night in the forest", "exploring a cave").
- `chapters`: 5-8 items [{"t": "h:mm", "label": "..."}], first one "0:00"; labels 2-5 words, concrete, in English.
- `thumb`: 3 candidate times "h:mm" for the thumbnail frame, best first, each with a 5-word reason. A good thumbnail frame is bright and colourful, one clear subject (a finished build, a boat at sunset, a lit house at dusk), no inventory/menus, not a close-up of dirt or stone.
- `title_idea`: <= 60 characters, standalone, specific and inviting (what happens), no part numbers, no version, no hashtags.
Final reply: one JSON object {"ep01": {...}, ..., "ep25": {...}} and nothing else. No push needed.
