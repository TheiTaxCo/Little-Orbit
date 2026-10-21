# Little Orbit · Version 2.1 · Female Spanish voice

Five gentle learning games for ages 3–5. This release combines the iOS icon, Memory Garden progression, fifth-game, and bilingual updates in one package.

## Update your existing GitHub deployment

1. Extract this ZIP on your computer.
2. Put **all extracted contents directly in your repository root**, replacing the matching previous files. Do not upload the ZIP itself or put the files inside an extra folder.
3. Include the updated `.github/workflows/deploy-pages.yml`. It publishes the new icon and manifest files along with the game. Merge `.github` with your existing directory rather than deleting other workflows.
4. Commit and push to your default branch.
5. Wait for the Pages deployment to finish. Your existing game URL stays the same.

Keep your existing Pages publishing source. The included workflow supports **GitHub Actions** publishing; **Deploy from a branch** also works when all files are in the branch root. If you use a different custom workflow, ensure it publishes all the icon and manifest files listed below.

### Hidden files

Files beginning with a dot can be hidden in your computer's file picker. On macOS, Command + Shift + Period reveals them in Finder. If necessary, use GitHub's Add file → Create new file, enter `.github/workflows/deploy-pages.yml`, and paste the matching workflow from this package. Replacing only `index.html` is not sufficient for the icon update.

## English and Spanish

Open **For grown-ups → Language / Idioma** and choose **English** or **Spanish / Español**. The choice is saved in the same browser. In Spanish mode, the grown-up button is **Para adultos**.

- All five games provide Spanish instructions, questions, number words, picture names, and reward messages.
- The home screen and grown-up guidance also switch languages.
- **Hear a sample / Escuchar una muestra** lets you test the selected voice.
- Changing languages preserves the current board, answer, and earned stars.
- Spanish speech automatically prefers recognized female voices, prioritizing enhanced/natural versions and Mexican Spanish when available.
- Open **For grown-ups → Spanish voice** (or **Para adultos → Voz en español**) to keep **Automatic · Female** or choose a voice and hear its sample. The choice is saved.
- Automatic selection uses a shortlist of recognized female voice names because browser speech metadata has no gender field. Other Spanish voices are labeled Preview rather than assumed female. If there is no recognized female voice, the app asks you to enable one or preview and choose a voice; it does not silently substitute a male voice.
- Spanish uses a natural pitch and a slightly slower reading pace for clarity. English behavior stays the same. Speech is never routed to an English voice while Spanish is selected.

Speech uses the device/browser's available voices. If no matching voice is available, the overlay explains that a voice must be enabled on the device. In that case, the game remains playable with translated text. Voice availability, voice quality, and offline speech vary by device and browser. Voice packs available to the operating system are not always exposed by every browser. Actual pronunciation and playback should be checked on your daughter's device using the sample button.

## iPhone/iPad Home Screen icon

After deployment, open the live game in **Safari → Share → Add to Home Screen**. The shortcut is named Little Orbit and has a friendly planet icon. If an existing shortcut retains an old icon, remove it, refresh the live game, and add it again.

The package includes iPhone/iPad PNG icons, a browser SVG favicon, PNG/ICO favicons, and 192/512-pixel manifest icons. All asset and launch paths are relative, so they work under a GitHub repository URL.

The manifest provides icon and launch metadata. This release does not add a service worker or guarantee offline loading of the hosted game. The game still runs locally from `index.html`; keep all files together to use the icons.

## Memory Garden

**Next discovery** is visible during play. Find every pair to enable it. The pair counter updates as you match cards. When a board is complete, the button is brought into view and advances to a fresh, shuffled board.

After five boards, **Finish adventure** opens the reward screen. **Keep matching** starts another five-board adventure. In Spanish these actions are **Siguiente descubrimiento**, **Terminar aventura**, and **Seguir jugando**.

Incomplete boards cannot advance. Stars are awarded once per completed board.

## Fifth game: Size Safari

Compare cheerful bunnies, fish, and butterflies. Each board uses the same animal at different sizes so children focus on comparing size.

| Level | Challenge |
| --- | --- |
| Age 3 | Two animals; find big or small |
| Age 4 | Three animals; find big or small |
| Age 5 | Three animals; find big, medium, or small |

Spanish prompts use grande, pequeño/pequeña, and mediano/mediana to match each animal. Each adventure contains five rounds with gentle retries and star rewards.

## All five worlds

1. Star Counter / Cuenta Estrellas
2. Color Pop / Colores Felices
3. Shape Explorer / Explora las Formas
4. Memory Garden / Jardín de Memoria
5. Size Safari / Safari de Tamaños

The game supports responsive layouts, large tap targets, keyboard controls, labels, and reduced motion. There are no timers, ads, purchases, or accounts.

## Package contents

| Path | Purpose |
| --- | --- |
| `index.html` | Complete game with both languages |
| `.github/workflows/deploy-pages.yml` | Publishes game, icons, and manifest |
| `.nojekyll`, `.gitignore` | Static publishing and local file exclusions |
| `favicon.svg`, `favicon.ico` | Vector/browser icons |
| `favicon-16x16.png`, `favicon-32x32.png` | Browser PNG icons |
| `apple-touch-icon.png` | 180-pixel iPhone/iPad icon |
| `apple-touch-icon-167x167.png` | 167-pixel iPad icon |
| `apple-touch-icon-152x152.png` | 152-pixel iPad icon |
| `icon-192.png`, `icon-512.png` | Manifest icons |
| `site.webmanifest` | App name, icon paths, and standalone display |
| `README.md`, `CHANGELOG.md` | Instructions and release notes |

## Settings and privacy

The release retains the existing `little-orbit-v1` storage key and adds a language preference. Existing stars and settings are preserved when the game is opened at the same URL in the same browser storage context. Home Screen apps may use a separate storage context; progress is not synced between devices. Storage-disabled browsers can still play with temporary visit progress.

The game sends no player information or analytics. The device/browser controls speech processing and voice availability. GitHub handles hosting traffic under its own policies. No external fonts, game libraries, APIs, or runtime dependencies are needed.

## Validation

The release passed voice-selection checks for female preference, enhanced voice priority, male-only and unknown-voice lists, explicit selection, persistence, and delayed voice availability, plus 150 simulated rounds across five games, three ages, and two languages. Checks covered retries, matching, progression, duplicate answers, navigation, storage-disabled play, live language switching, Spanish vocabulary, voice language selection, and avoiding an English voice when Spanish is selected. Icon dimensions, relative asset links, manifest entries, workflow staging, and ZIP integrity were also checked.

The workflow has not been run in your repository. Visual browser, touch, speech playback, and iOS Home Screen installation testing remain to be completed on your devices.

## References

- [Apple: configure web applications and Home Screen icons](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)
- [GitHub: configure Pages publishing](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [Browser voice selection](https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/voice)
