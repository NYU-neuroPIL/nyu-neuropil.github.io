**NOTE**: this is the github repository for the website, to see the website
itself, go to [nyu-neuropil.github.io](https://nyu-neuropil.github.io/).

# NYU neuroPIL

# Updating

Several parts of this website can be edited without going into the code:

- Publications: complete this [google
  form](https://docs.google.com/forms/d/e/1FAIpQLSet7MgMnwAdpY5p3Hdb1crMlhp2sH7dvEd0bJWlff2oHC_q2g/viewform?usp=sf_link)
  in order to add a publication. You have to sign in to a google account, but I
  think any account works (i.e., doesn't have to be `@nyu.edu`)
- Application FAQs: update [this google
  sheet](https://docs.google.com/spreadsheets/d/1t2ruBzuom-9EhSb6YIMXFETrx0PvZsfQts-WLkPN9LY/edit#gid=0);
  you'll need to be signed into either the `neuropilwebsite` or
  `neuropilcouncil` gmail address to do so. In the answers, you'll need to use
  HTML syntax to get text formatting (e.g., bold, lists, paragraph breaks). See
  [here](https://www.w3schools.com/html/html_formatting.asp) for basic text
  formatting and if you need something else, searching `html text __` will
  generally bring up an answer.
- Adding pictures to carousel: this is slighlty more complicated. You'll need to
  have a GitHub account and get added to the
  [NYU-neuroPIL](https://github.com/NYU-neuroPIL) group by someone already in
  it, then upload pictures to the
  [Pictures](https://github.com/NYU-neuroPIL/nyu-neuropil.github.io/tree/master/Pictures)
  folder. Finally, open up `index.html` and find `<div class="carousel-inner">`
  (on 2021-10-22, this starts on line 276). At the end of this block, add a new
  `div` for your new picture:

  ``` html
  <div class="item" style="margin-top:0px;">
    <img class="center-block" src="./Pictures/C16.PNG" alt="c16" style="height:150px;" >
  </div>
  ```
  
  replacing `C16.PNG` with the name of your new picture and `alt="c16"` with
  the name, in lower-case and without the extension.


# For local preview

In order to preview locally, you'll need to [setup a local testing
server](https://docs.google.com/document/d/15pFbnUiX-Nd0Y1YtzD-uAFq6LWTmfCr239RbtlZluGc/edit#). Basically
that just means having a basic Python 3 install, navigating to this
directory, and running `python -m http.server`.

  
# Internal info

 - info about housing (up and down town) and insurance with domestic
   partners / spouses

# API Key restriction

in order to access the Google Sheet where we store everyone's
publication information, we need to use an API key from
Google. Because we're using Github pages, we have no way of making
that private, so instead we have its settings such that it only honors
requests from the NeuroPIL website (`nyu-neuropil.github.io`). **This
means it won't work if you're testing it locally!** In order for it to
work locally, log in to the `neuropilwebsite` Google account, then go
to the
[Credentials](https://console.developers.google.com/apis/credentials/)
page, click on the `NYU NeuroPIL Publications` API key, and set the
`Application restrictions` option to `None`. **When you're done,
remember to re-enable it**, by going to the same place, picking `HTTP
referrers` instead, and entering `nyu-neuropil.github.io/*` as the
website.

Note that if we ever change the url of the website, we'll need to do
this as well.

# Template details

Template Name: Amoeba - v2.0.0

Template URL: https://bootstrapmade.com/free-one-page-bootstrap-template-amoeba/

Author: BootstrapMade.com

License: https://bootstrapmade.com/license/

# Structure

- Homepage
  - with a quick blurb about what we are and links to a couple
    relevant things
- Menu (across the top right of page)
  - More info (drop down menu):
    - About: More details about neuroPIL/about us
    - NeuroPIL Council: Profile of executive council
  - Publications
    - blog style posts every month or so with pdf of paper attached
      - Would potentially want tags for labs to sort publications
  - Contact Us: fillable form that feeds into
    neuropilcouncil@gmail.com (mentioned in meeting)
  - Other: (drop down menu):
    - Outreach Opportunities: page
    - For students
      - Prospective
      - Incoming: timeline of program, etc  
      - Current
    - Links page with all “relevant” websites to all the program pages

- Resources sections: links NOGN, ScAAN, and other groups students are
  part of (GSOC)

# Todos

website for NYU neuroPIL. As of summer 2020, we've pretty much stopped working
on these.

To do:

1. [ ] put together publications page, (see
   [example](https://www.dudmanlab.org/html/publications.html)) --
   Billy
   - [X] put together Google form (or similar) asking for: title; one
     sentence summary; summary picture; tags for topics, techniques,
     labs; links (paper, bioRxiv, code/data, reprint)
   - [X] work on something that renders Google form output to what we
     want -- right now, can save manually as csv then add to repo and
     push.
   - [X] see if can automate submission of Google form to adding data
     to github repo
     - [X] we now have it automatically populating a Google Sheet
     - [X] having trouble changing the sharing parameters (we think we
           need to change neuropilweb gmail account from managed by
           council? it's setup as a child account) -- fixed this by
           creating a new, non-child account
     - [X] once that's done, set up using
           [Tabletop](https://github.com/jsoma/tabletop) (or actually
           PapaParse) and grab data from it in the javascript
       - [X] following [instructions
             here](https://github.com/jsoma/tabletop/issues/189) to
             get around CORS policy error, which required [creating a
             new
             project](https://stackoverflow.com/questions/31869154/you-do-not-have-sufficient-permissions-to-view-this-page)
             in the Google APIs thing (and switching the permissions
             on the Sheet so that anyone with the link can access)
   - [X] get text centered
   - [X] make link go to paper or preprint
   - [X] redo format to use cards, add icons for different links
   - [ ] longer-term goal: click on card and get a mini-blog post
   - [ ] tagging:
      - [ ] add extra tags (labs, techniques)
      - [ ] allow multi-select (both within and across?)
   - [ ] put limit on number that are displayed or scroll or something
   - [X] add subtitle with author and year
   
4. [X] Make contact form live -- Jenn
2. [X] Embed Twitter feed -- waiting for twitter account
3. [X] Fill in information
   - Executive council: coming soon
   - FAQ: Katie, Chloe, etc
   - resources -- Ionatan
4. [X] Change color palette -- Jenn
5. [X] Get photo for background -- Ionatan. should be ~1580 by 860
       pixels, probably no text
6. [X] put mini logo on top banner
6. [X] get logo -- Katie
7. [ ] photo carousel with social photos from Google Drive (replace
       the charter picture)
8. [X] add committee info
8. [X] remove map at bottom
9. [X] try and break up into separate html files -- Billy -- Actually,
   this is probably fine as long as we document it and write up
   directions well, so probably ignore
7. [ ] add directions for editing and updating
8. [ ] fix on mobile:
   - [ ] navbar not visible
   - [ ] spacing doesn't look quite right
9. [ ] Add link to Github?
9. [ ] get shorter text for about us and put centered, right under "about us",
       and above photo carousel and twitter feed
