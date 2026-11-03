# Muscle Atlas

A rotatable 3D model of the human bones and muscles for studying BIOL 232 (Human Anatomy and Physiology I) at Eastern Washington University. Tap any bone or muscle to see what it is, its origin, insertion and action, and which bones and muscles it connects to. Quiz mode tests names, locations, origins, insertions, actions and bone purposes.

## Run it in VS Code

The page loads its 3D data with `fetch`, so it has to be opened through a local web server. Double-clicking `index.html` will not work.

**Option 1: Live Server extension (easiest)**

1. In VS Code, open the `muscle-atlas` folder (File → Open Folder).
2. Install the **Live Server** extension by Ritwick Dey (Extensions panel, search "Live Server").
3. Right-click `index.html` and choose **Open with Live Server**.

**Option 2: Terminal**

Open a terminal in the `muscle-atlas` folder and run one of these:

```
python -m http.server 8000
```

or

```
npx serve
```

Then open http://localhost:8000 (or the address `serve` prints) in your browser.

## Put it online with GitHub Pages

1. Create a new repository on GitHub.
2. Click **uploading an existing file**, then drag in everything inside the `muscle-atlas` folder (`index.html`, `flat.html`, `README.md`, and the `data` and `vendor` folders). Commit.
3. Go to **Settings → Pages**, set Source to **Deploy from a branch**, choose `main` and `/ (root)`, and save.
4. After a minute the site is live at `https://YOUR-USERNAME.github.io/REPO-NAME/`.

## What's in the folder

| Path | What it is |
| --- | --- |
| `index.html` | The 3D atlas (viewer, study panel, quiz) |
| `flat.html` | The simpler 2D study plates |
| `data/facts.js` | Study facts: origin, insertion and action for each muscle; location, purpose and length for each bone. Edit this to match her textbook. |
| `data/manifest.json` | List of every 3D part and where its shape is stored |
| `data/*.bin` | Compressed 3D shapes for bones, muscles, cartilage and tendons |
| `vendor/` | three.js r147 (3D library), so the page works offline |

## Editing the facts

Each muscle in `data/facts.js` looks like this:

```js
'biceps brachii':['Arm','Origin text','Insertion text','Action text'],
```

Change the text and refresh the browser. Keep the name on the left exactly as it is, since it links the facts to the 3D model.

## Credits and licences

- 3D anatomy: **BodyParts3D**, © The Database Center for Life Science, licensed under Creative Commons Attribution-ShareAlike 2.1 Japan (https://creativecommons.org/licenses/by-sa/2.1/jp/deed.en). Source: https://lifesciencedb.jp/bp3d/. The models were simplified (fewer triangles) and repacked for the web. If you share a modified version of the 3D data, it must keep this credit and the same licence.
- three.js: © 2010–2022 three.js authors, MIT licence (https://github.com/mrdoob/three.js).
- The dataset does not include the six ear ossicles or the coccyx. Bone lengths are rough adult averages; go by the textbook if it differs.
