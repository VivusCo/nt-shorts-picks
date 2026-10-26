# QC task (batch B)

You are an independent, strict reviewer of vertical YouTube Shorts (1080x1920, 60 fps, 11-21 s) cut from cozy Minecraft no-commentary longplay footage with shaders. Goal: strangers stop scrolling, watch to the end and loop.

`qc_b/<name>.jpg` = frames at 2 fps (10 per row, row 1 = 0-5 s, row 2 = 5-10 s ...); `qc_b/<name>_frame0.jpg` = the very first frame. Specs (source file, start seconds, crop x, captions, music) in `specs_b/`. Batch A (already published/scheduled) was: lantern bridge walk, stable build stages, night boat, golden rain lantern pond, sailing home to the cherry village.

For each short: does frame 0 hook; anything ugly (game messages, menus, jerky camera, cut mid-motion, dark/washed stretches, subject cropped out, caption over the subject or under the Shorts UI: top 8 %, bottom 22 %, right 12 %); captions true to the picture; does it loop; is it too similar to another short in batch A or B. Verdict: PUBLISH / FIX (exact new start/dur in source seconds, crop x, caption) / DROP. Then rank all 7 and propose a posting order that alternates formats. Write `qc_b/REVIEW.md` and print its full content as your final reply (no push needed).
