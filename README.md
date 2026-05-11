# Last Orders — Local Demo

A B2B operator pitch demo for **The Crown**, a closing-time betting game by MK19 Labs.

## To run

### Mac

1. Double-click **`run_demo.command`**
2. The first time, macOS may say "cannot be opened because the developer is unverified" — right-click the file, choose **Open**, then click **Open** in the dialog. (Only needed once.)
3. Your browser opens the demo. Keep the Terminal window open while you use it.
4. Close the Terminal window when you're done.

If `run_demo.command` won't execute, open Terminal in this folder and run:
```
chmod +x run_demo.command
```

### Windows

1. Double-click **`run_demo.bat`**
2. A black command-prompt window opens — that's the server.
3. Your browser opens the demo. Keep the command-prompt window open while you use it.
4. Close the command-prompt window when you're done.

If it complains about Python missing, install from <https://python.org> and tick "Add Python to PATH" during installation.

### Why do I need this script?

Modern browsers block local file access for security (the `file://` protocol can't load video files). The script starts a tiny local web server so the browser treats this like a real website. The server only runs on your machine — nothing is uploaded.

## Folder contents

```
last_orders_demo.html    The demo
clips/                   Video clips (6 included)
run_demo.command         Mac/Linux launcher
run_demo.bat             Windows launcher
README.md                This file
```

## Adding more clips

Drop new MP4s into the `clips/` folder, then edit the `clipFiles` block near the top of the `<script>` section in `last_orders_demo.html`:

```js
clipFiles: {
  0: ['clips/empty_01.mp4'],
  1: ['clips/one_01.mp4'],
  2: ['clips/two_01.mp4', 'clips/two_02.mp4', 'clips/two_03.mp4'],
  3: ['clips/three_01.mp4'],   // add this when you have it
  4: ['clips/four_01.mp4'],
  5: ['clips/five_01.mp4'],    // add this when you have it
},
```

Also add the new counts to `allowedParts: [0, 1, 2, 4]` — e.g. `[0, 1, 2, 3, 4, 5]` once all counts have video.
