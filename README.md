# Fix Our Friendship 🎮🤝

A tiny 4-level game drawn in a scribbly coloured-pencil style. She has to finish every level to unlock the last question: **"So… friends again?"** There are no hearts anywhere, just friendship things like momos, pizza, our songs, co-op games, bracelets, puzzle pieces and paper-plane notes.

0. **My room (the map)**: your drawing (`assets/room.jpg`) with numbered markers on things in the room. She taps the controller, the notes on the wall, the moon poster, the window and finally "me on the sofa". Below the drawing is a list of the same levels as hand-drawn cards, with the stars she's earned. Progress is saved in her browser, so a refresh doesn't lose it.
1. **Catch our good stuff**: friendship doodles fall into a cardboard **US** box. Catching 5 in a row is a combo and gives a bonus point, and a gold star counts double. Catching a grumpy cloud or a `#@!` fight bubble costs a point.
2. **Our memory wall**: sticky notes flip over in 3D to show polaroids. When she finds a pair, it gets pinned to the wall and one of your memory notes pops up ("Remember when…"). Matches in a row build a streak.
3. **Fix our picture**: a scribbly picture of "US" (bunting, a night window, two mugs on the blue sofa) is cut into a sliding puzzle: 8 pieces and one gap. She taps a piece next to the gap to slide it in, and once every piece is home the last one fades in and the picture gets taped back together. Every scramble can be solved in 10–16 moves, and the counter shows the fewest possible.
4. **Spell it out**: 3D toy letter blocks spell `FRIENDS`, with 2 fake blocks mixed in. A wrong block just shakes and says "nope!".
5. **Last page**: a notebook page flips over to ask the question. "No" pleads twice and then runs away. "Yes" makes friendship doodles rain down and shows your ending message.

Each level gives **1–3 stars** for how well she did, and using a hint caps it at 2. She can't lose a level. If she's stuck for 40 seconds or keeps missing, a **"stuck? get a hint 💡"** note appears: easy mode in Level 1, a quick peek at all the cards in Level 2, the next 4 correct slides done for her in Level 3, the next block lit up in Level 4.

## 1. Personalize it

Open `index.html` and edit the `CONFIG` block at the top of the `<script>`:

- `name`, `fromName`: her name and yours
- `roomCaption`: the line under the room drawing
- `levels`, `finalSpot`: level titles and which thing in the room opens each one
- `catchGoal`: how many good things she needs to catch in Level 1
- `memories`: the 6 pairs for Level 2. Each has an `icon` (one of `momo`, `pizza`, `icecream`, `popcorn`, `mug`, `headphones`, `controller`, `plane`, `bracelet`, `puzzle`, `polaroid`), a short `text` caption and a `note` that pops up when she matches the pair. **Make these about the two of you!**
- `pictureCaption`: the little line under "US" in Level 3
- `magicWord`, `magicHint`, `decoys`: the Level 4 word (letters only, max 10), its clue, and how many fake blocks to add (0–4)
- `question`, `noReplies`, `runawayLabels`, `yesTitle`, `yesSub`: the last question and the ending
- `hintAfter`, `sound`: how many seconds before a hint is offered, and whether the sounds start on

To use a different room drawing, replace `assets/room.jpg`. If you do, move the markers by editing `SPOTS` in the map code: each one is `[left %, top %]` on the picture.

## 2. See which level she's on (phone notifications)

1. Install the **ntfy** app ([Android](https://play.google.com/store/apps/details?id=io.heckel.ntfy) / [iPhone](https://apps.apple.com/app/ntfy/id1625396347)).
2. Subscribe to the topic in `CONFIG.ntfyTopic` (`friend-game-7c41e9a2d05b` right now), or watch it at https://ntfy.sh/friend-game-7c41e9a2d05b
3. You'll get alerts like:
   - `👀 Jasmine opened the friendship game (phone)`
   - `▶️ Jasmine started Level 2: Our memory wall`
   - `✅ Jasmine cleared Level 2: Our memory wall ⭐⭐☆ in 48s (11 tries for 6 pairs, 1 hint)`
   - `👋 Switched away during Level 3: Fix our picture (21s in)`
   - `🔓 Jasmine unlocked the final question!`
   - `🤝 Jasmine said YES to being friends again! 🎉 (after pressing NO 2 times)`

Anyone who knows the topic name can read it, so keep it private. Set `ntfyTopic: ""` to turn alerts off, and `showTrackingNote: false` to hide the "this game tells … which level you reach" line.

To play through it yourself before sending, use **start over** at the bottom of the map to reset the progress saved in your browser.

## 3. Share it

The game is `index.html` plus the `assets` folder, so keep them together. Host the `mini game` folder (or the whole `3dpage` folder) for free and send her the link. The easiest way is to drag the folder onto https://app.netlify.com/drop. GitHub Pages or Vercel also work.
