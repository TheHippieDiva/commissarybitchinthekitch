# commissarybitchinthekitch.com

The book's own one-page site: **Commissary B\*tch in the Kitch** by Dawn de Brantes (TheHippieDiva).
Static HTML + CSS, made for free GitHub Pages hosting. Built 11 Nov 2026, LOCAL ONLY: no repo, no push, no DNS yet.

Design: storyboard direction B + C combined (Dawn's pick), from
`TheHippieDiva-channel/brand/website/commissary-domain/board_src.html`.
Copy reused from the live book page (`.../website/commissary/commissary-block.template.html` + `make_commissary_downloads.py`).

## Files
- `index.html` : the page (SEO title, meta description, Book JSON-LD, OG/Twitter card)
- `assets/site.css` : light default, dark via prefers-color-scheme, print = black on white
- `assets/book-cover_chalk_640.jpg` : cover (drawing by Shawna)
- `CNAME` : `commissarybitchinthekitch.com`
- `_previews/` : headless Chrome renders (390 + 1280, light + dark) and a print PDF. Not needed on the live site.

## Page sections
1. Wall (cinder block): headline "Dinner was contraband. Now it's a cookbook.", title, buy buttons, #1 New Release stamp, cover
2. Commissary sheet: "Tonight's order" = the Prison Wraps ingredients from the book (p. 30), plus Dawn's locked blurb line
3. Recipes, Going in?, A gift for someone in prison, Free gifts, About Dawn, Questions
4. More from Dawn (thehippiediva.com/cookbook + /free-gifts), footer

## Going live later (only when Dawn says go)
1. New GitHub repo, push this folder's contents (skip `_previews/` if wanted).
2. Settings > Pages > deploy from branch `main`, root.
3. At the domain registrar: A records to GitHub Pages IPs (185.199.108.153, .109, .110, .111) and `www` CNAME to `<user>.github.io`.
4. Tick "Enforce HTTPS" once the certificate is issued.

## Re-render previews
```
C="/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"
"$C" --headless --hide-scrollbars --virtual-time-budget=6000 --blink-settings=preferredColorScheme=1 --window-size=1280,2800 --screenshot=_previews/cbitk-site_1280_light.png "file://$PWD/index.html"
"$C" --headless --no-pdf-header-footer --virtual-time-budget=6000 --print-to-pdf=_previews/cbitk-site_print.pdf "file://$PWD/index.html"
```
(`preferredColorScheme=0` = dark. For 390 wide, Chrome's window can't go that narrow: load the page in a 390px iframe and crop.)
