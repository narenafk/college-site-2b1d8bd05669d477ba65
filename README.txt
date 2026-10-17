SKASC Hack in a Day - Track 3 - Ship the College Site Automatically with GitHub Actions
Starter files

WHAT IS IN THIS FOLDER
  site\index.html   The page. It shows the college name, your participant code and the lab timings table.
  site\app.js       Reads data.json and fills the page. You do not need to change it.
  site\data.json    The only file staff edit: college name, code and lab slots.
  deploy.yml        The GitHub Actions workflow. You paste its text into GitHub in Milestone 3.
  README.txt        This file.

HOW TO USE THEM
  1. Download this whole folder to your lab desktop (for example to Downloads).
  2. In Milestone 2 you drag the "site" folder (the folder itself, not the files inside it)
     onto the GitHub "Upload files" page. GitHub then keeps the path site/index.html, site/app.js
     and site/data.json. The workflow uploads everything inside site.
  3. In Milestone 3 you open deploy.yml in Notepad, copy all of it, and paste it into the
     GitHub workflow editor. Name the file deploy.yml.
  4. From then on you only edit site/data.json in GitHub. Every commit to main deploys the site.

GOOD TO KNOW
  - Opening index.html straight from your computer shows "Loading lab timings..." or
    "Could not load data.json". That is normal: browsers block a page from reading local files.
    The page works once it is on Azure Storage.
  - data.json must stay valid JSON: keep the quotes, commas and brackets. Each lab slot looks like:
      { "name": "Computer Lab 1", "opens": "09:00", "closes": "11:00" }
    Put a comma between slots, and no comma after the last one.
  - build.json does not exist in these files. The workflow writes it on every run with the commit
    it deployed.
  - Never put the SAS token in any file. It belongs only in the GitHub secret AZURE_SAS_TOKEN.

Your repository is yours. Keep it as a portfolio piece or delete it after the event.
Deploys stop working after today because the SAS token and the lab storage account expire.
