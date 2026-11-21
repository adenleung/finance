# Chiikawa Finance Club — Little Orchard Village

## Play
Open **dist/index.html** in a desktop browser. The game, fonts, art, audio and all lessons work offline. A mobile file viewer may display a preview without running JavaScript. For mobile play, serve the dist directory and visit it in Safari or Chrome. From this folder, run `python -m http.server 8000 --directory dist` and open http://localhost:8000 on the same computer. No account, API key or installation is needed to play.

Choose the pink Money Garden and then **The first money seed**. Grow the 100-coin seed twice. Watch the second year's 11 coins appear, ask Moss for the explanation, then try different values independently. The other buildings are open from the start for revision.

## Map and story
Pip, a cream mouse with a strawberry beret, wants to buy lanterns. Moss, a raccoon with a ledger, helps the village compare financial choices. Clover, a lop rabbit, keeps an eye on the festival business. Their original portraits appear in the map, dialogue and residents gallery.

| Chapter | Missions | Village project |
|---|---:|---|
| Money Garden | 14 | Fund the lanterns and grow the coin orchard |
| Bond Bank | 9 | Price the council's bridge financing |
| Equity Market | 12 | Help the bakery and compare market valuations |
| Planning Office | 9 | Fund a community centre |
| Finance Festival | 10 linked decisions | Award a village adviser certificate |

A flower appears for each completed lesson. Finishing a chapter adds its illustrated improvement. Finishing the festival adds bunting and opens advanced revision.

## Learning and saves
Each lesson moves through a story prompt, an adjustable workbench, a plain-language explanation, guided practice, two independent calculations and an application question with interpretation. Values change between stages. One independent question also asks for a method. Hints and a worked example are available. Opening independent support rotates the scenario. New mastery awards one star and 20 coins. The festival unlocks after all 44 stars and pays 100 coins once. Opening a completed notebook entry allows extra practice without duplicate rewards.

The notebook displays formulas, assigned slide pages, warnings, examples and Excel expressions. All entries are available immediately through All revision notes. Some spreadsheet examples are illustrative equivalents. Percentage answers use percentage points as displayed (enter 5 for 5%). Enter plain numbers rounded to two decimal places. Money flows in the village are expressed as positive magnitudes unless a question says otherwise.

The versioned local save stores topic phase, scenario seed, attempts, errors, hints, time, accuracy counts, last submission, latest mission, festival stage and preferences. Close the settings dialog with Escape. Export a save before clearing browser storage or moving to another device. Import previews the replacement. On mobile, private browsing or file URLs may provide limited storage.

## Source and extension
- `content.js` contains the 44 source-referenced narrative and question definitions. `CURRICULUM.md` maps activities to pages.
- `finance.js` implements growth, discounting, equal-payment streams, coupon bond pricing, bracketed YTM, dividend valuation, CAPM and WACC.
- `labs.js` and `labs.css` implement the interactive workbenches and their accessible numerical equivalents.
- `state.js` defines save validation, mastery, rewards and the festival.
- `app.js` handles navigation, story dialogue, practice feedback and settings. `audio.js` synthesises original soft notes locally after an interaction. `scenery.js` draws persistent map upgrades.
- `village.svg`, `pip.svg`, `moss.svg` and `bun.svg` are editable original artwork. `style.css` contains the interface design. `template.html` supplies the page shell.
- To add a lesson, add a unique ID to the appropriate chapter in `content.js`, add its workbench in `labs.js`, and provide 9 numeric variants, interpretations and a source page. Update the explicit expected mission counts in the tests and documentation. Preserve old IDs when extending existing saves.
- Rebuild offline HTML using `python build.py`. For deployment, serve dist/index.html as a static file. No server-side data collection is required.

## Tests
Run `node test.cjs` for lecture examples, finance edge cases, mission integrity and save checks. It also regenerates the curriculum matrix. To run the isolated full-game browser check, run `python qa.py` and open dist/qa.html. This test creates a 390px-wide game with isolated storage, drives all 44 missions through their controls and completes the festival. It leaves your own progress untouched.

A separate Playwright suite in `test_browser.py` covers a page reload, downloads and save-file import. Install Python Playwright and its Chromium browser to run `python test_browser.py`, or set CHROMIUM_PATH to an existing Chromium executable.

## Scope of this build
The release uses dependency-free browser JavaScript and SVG, with original vector scenery and local audio. Workbenches share reusable illustrations. Resident movement uses a limited set of expressions and transitions. Buildings open into illustrated interior vignettes, mission boards and workbenches. Reasoning checks use structured choices. The full cinematic character animation library, freely explorable building interiors, and free-text assessment are outstanding. Browser timings and motion have not been certified on physical iPhones or lower-powered laptops.

## Attribution
This is an unofficial, personal educational fan project. Chiikawa and franchise names belong to their respective owners. All village illustrations, the three substitute residents, diagrams, sound design, story dialogue and practice scenarios were created for this project. The supplied reference was used for visual direction and is not bundled. Four user-supplied NYP BM4119 lecture PDFs inform the educational content and page references. The source PDFs are not redistributed.

Nunito is bundled under the SIL Open Font License, Version 1.1. See fonts/nunito-OFL.txt. Font source: https://github.com/google/fonts/tree/main/ofl/nunito.
# finance
