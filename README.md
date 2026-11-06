# CampusBridge

A college discovery website for international students exploring study options in India.
Created by Rajdip Sarker.

## Included version

Exported on 6 November 2026 from source commit `48b81183436bd75aaac576f3e59d20db066e87a6`.
The directory contains 135 institutions across 20 Indian states and territories, including 57 in West Bengal.

## Run locally

No framework, npm packages, build step, database, or API key is required.

1. Extract this ZIP.
2. Open a terminal in the `campusbridge` folder.
3. Run `python -m http.server 8000` (on Windows, `py -m http.server 8000` also works).
4. Visit http://localhost:8000 in your browser.

You can also open `index.html` directly, but a local server is recommended for consistent browser storage behavior. Internet access is required for external photos, fonts, official links, and maps.

## Project files

- `index.html`: page structure and responsive CSS.
- `app.js`: search, filters, profile dialogs, map links, comparison and shortlist behavior.
- `colleges.json`: editable institution records.
- `data.js`: generated browser-readable copy of the records.
- `scripts/sync_data.py`: validates records and regenerates `data.js` after edits.
- `.gitignore`: excludes common local files and secrets.
- `.nojekyll`: allows straightforward static hosting on GitHub Pages.

## Features

- Search university names, common aliases, cities, states and recorded courses.
- Search suggestions and equivalence for terms such as CSE and computer science.
- State, institution type, course level and fee-information filters.
- Profile tabs for overview, courses and fees, faculty links, admissions and location.
- Comparison of up to three institutions.
- Saved shortlist and student checklist stored locally in the visitor's browser.
- Google Maps search and directions links, with selectors for selected multi-campus institutions.

## Edit university information

Edit `colleges.json`, then run:

```sh
python scripts/sync_data.py
```

Commit both `colleges.json` and the regenerated `data.js` together. Each institution needs a unique `id`. Preserve existing IDs so saved shortlists continue to work. Preserve source and photo attribution fields.

The script checks required fields, duplicate IDs and valid map targets. It does not verify the factual accuracy of the data.

## Upload to GitHub

1. Create a repository in your GitHub account, for example `campusbridge`.
2. Extract this ZIP on your computer.
3. In the repository, select **Add file → Upload files**.
4. Upload the contents of the extracted `campusbridge` folder, including the `scripts` folder. Put `index.html` at the repository root; do not upload only the ZIP.
5. Commit the uploaded files.

Alternatively, from the extracted folder:

```sh
git init
git add .
git commit -m "Add CampusBridge college directory"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
git push -u origin main
```

Replace the URL with your own empty repository's URL. Authenticate using GitHub's normal sign-in flow; do not place passwords or access tokens in these project files.

## Optional GitHub Pages hosting

In the repository's **Settings → Pages**, choose deployment from a branch, select `main` and the root folder, and save. GitHub will show the website URL when deployment completes. Availability depends on the repository and account settings. Enabling Pages can make the website publicly accessible; choose repository and hosting visibility deliberately.

This export is independent of the private ChatGPT Sites deployment. Uploading or editing it on GitHub does not automatically update that deployment, and future Sites edits do not automatically sync to your GitHub repository.

## Data limitations

This is a directory prototype, not a complete admissions database.

- All requested university names are represented, but most course catalogues, faculty details, international fees and deadlines remain unverified.
- New listings have clearly labelled photo placeholders until a suitable image is verified.
- Programme fees shown for selected courses are not necessarily annual fees or international-student quotes.
- Eligibility and scholarships must be confirmed with the institution.
- Map embeds and links use campus names/localities and selected sourced postal addresses. Exact map pins are not independently verified. The project does not include a keyed Google Maps JavaScript or Places API integration.
- External images may fail to load, and embedded maps may be blocked by browser/network settings. Source and direct map links provide fallbacks.
- No login, backend, application submission, server database or scheduled data refresh is included.

## Image credits and licensing

Campus photographs remain externally hosted. Attribution and source links are retained in each record and displayed in the interface. Third-party images are not covered by a blanket project license; check permission or replace them with appropriately licensed photos before broader distribution. No open-source license has been selected for the project code in this export.
