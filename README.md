# offline-jupyter-slides
Configuration and files for offline Jupyter Notebook-derived reveal.js slides

## Usage
1. Convert your jupyter notebook to slides using the config file found in this
   repo (`offline-slides-nbconvert-config.py`):

```
jupyter nbconvert --to slides YOUR-NOTEBOOK.ipynb --config=offline-slides-nbconvert-config.py
```

2. Place the `static` folder from this repo in the same folder as your slides.
   
The `static` folder contains versions of all the javascript libraries, css 
stylesheets, and fonts that Reveal.js needs to make your slides work. The 
nbconvert configuration in step 1 updated the source links in your slides to 
expect everything as laid out in this `static` folder.

3. Serve your slides with a webserver.

## Optional
0. If you'd like to grab your own javascript dependencies from npm:

    - `npm install reveal.js`, move node_modules/reveal.js (the whole directory)
to static
        - You can probably remove everything but the `/dist` folder...
          probably.
    - `npm install jquery`, move node_modules/jquery/dist/jquery.min.js to static/
    - `npm install requirejs` (no dot!),  move node_modules/require.js static 
    - Don't forget the fonts from this repo's static/fonts folder!

    These dependencies appeared to work with the latest versions available on 
    npm as of 8 Feb 2021. YMMV!
