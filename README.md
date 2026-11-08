# Angelica Dornton — portfolio

The source for [dornton.vercel.app](dornton.vercel.app): Open the files with any static server and they run.


| File | Purpose |
| --- | --- |
| `index.html` | The main build. Navigation is a fake shell — you click or type commands. |
| `classic.html` | A calmer, document-style build of the same content. Reachable from "clean mode, STILL IN WIP!! |
| `site.css` | Styling |
| `app.js` | Terminal commands, section routing, and canvas/WebGL effects |
| `assets/cavalhatriz.woff2` | Pixel display face for the name heading |
| `assets/byron.woff2` | Script used once, for the signature at the end of the about section |
| `llms.txt` | Short plain-text summary for language models. |
| `sitemap.xml` | One URL, for search engines. |

## The terminal
Navigation is a real (if tiny) command layer. `cd` switches sections, `cat` opens a file, and the
sidebar's `$ help` is the hint
| Command | Does |
| --- | --- |
| `help` | Lists the available commands. |
| `ls [path]` | Lists a directory from the fake filesystem. |
| `cd /projects` | Jumps to a section (`/`, `/projects`, `/about_me.txt`, `/contact.txt`). |
| `cat about_me.txt` | Prints a file to the log and shows its section. |
| `pwd`, `whoami` | Print the working directory / user. |
| `clear` | Empties the log. |
| `clean` | Crossfades into `classic.html`. |
| `fx on\|off` | Toggles the background effects. |
## Effects

Four layers stack behind the content — a WebGL grain/noise shader, a Three.js grid that bends toward
the cursor, drifting tracked "blob" boxes drawn on a 2D canvas, and an ASCII portrait sampled from a
canvas at runtime

They degrade on their own:
- If the frame rate stays under 28fps for three seconds, all effects switch off and stay off.
- Touch devices skip the 3D grid and run the 2D layers at a reduced frame rate.
- `prefers-reduced-motion` skips the boot sequence and disables the animations.
- `fx off` turns the effects off by hand; `classic.html` is the no-effects build.
- 
## Deploying
The site is plain static files in the repository root, served by GitHub Pages. Commit the changed
files to the Pages repo and the site updates on the next Pages build

## Notes
The page ships a strict CSP: no inline scripts, no third-party analytics, no cookies. The only
external requests are Google Fonts, Three.js (cdnjs) and devicon icons (jsDelivr); the sticker is
hosted in `assets/` so it loads under `img-src 'self'`

## Contact

- Email: [aj-dornton@proton.me](mailto:aj-dornton@proton.me)
- GitHub: [github.com/eliutot](https://github.com/eliutot)
- Behance: [behance.net/angelicadornton](https://www.behance.net/angelicadornton)
- Figma: [figma.com/@dornton](https://www.figma.com/@dornton)
- Passportdex: [passportdex.com/angelicaa](https://passportdex.com/angelicaa)
