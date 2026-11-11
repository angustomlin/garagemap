# RMC Garage Network
A static UK trusted-garage map. No build step, API key, database or package installation.

## Deploy through Git and Netlify
1. Unzip this folder.
2. Create a GitHub repository and upload index.html, style.css, app.js, netlify.toml and this README to the repository root. Do not upload the ZIP itself.
3. In Netlify, import the repository as a new project.
4. Leave the build command empty. Set the publish directory to `.` (the repository root). The included netlify.toml also sets this.
5. Deploy. Future commits redeploy the app.

You can also drag the unzipped folder into Netlify's manual deploy screen.

## Use
- Add a garage name, full address and UK postcode. Postcode lookup plots a postcode-centre pin, not a precise workshop entrance.
- Save contact details, phone number, comma-separated specialists and internal notes.
- Edit or delete records from the list. Trusted pins are green; to-review pins amber.
- Enter a customer postcode to sort matching garages by straight-line miles. These are not road distances or journey times.
- Filter by specialist/status or search names, addresses, notes and postcodes.
- Directions open Google Maps using the garage's full address and name.
- Export a JSON backup regularly. Import merges by record ID, updating matching records and preserving other records.

## Storage and privacy
Garage data is saved in localStorage in the browser on the site's domain. It survives refreshes but is NOT shared between computers, browsers, staff or different site URLs. Clearing browser data removes it. Export before moving domains. There is no login or cloud database. Anyone using the same browser profile can see the saved list. The hosted app code is public unless you separately configure access controls with your host.

There are no preloaded or invented garages. Postcodes are sent to postcodes.io for lookup. Map tiles come from OpenStreetMap; Leaflet loads from unpkg. Internet access is required for the map and postcode lookup. The saved list and editing of unchanged postcodes remain available if lookup fails. Google Maps links send the selected address/postcode to Google when clicked. No live Google reviews or rating claims are included.

## Local development
Serve this folder with a static server, e.g. `python3 -m http.server 8000`, then open http://localhost:8000. No npm dependencies.
