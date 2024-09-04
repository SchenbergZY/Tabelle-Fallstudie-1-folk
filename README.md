# Difference from https://github.com/quadriga-dk/Tabelle-Fallstudie-1:

## 1. Edit .github/workflows/deploy-book.yml

###    Adding R installation after python setup announcement.

    - name: Set up R 
      uses: r-lib/actions/setup-r@v2
        
    - name: Install IRkernel
      run: |
        Rscript -e "install.packages('IRkernel')"

###    Register IRkernel after pip install requirments.

    - name: Register IRkernel
      run: |
        Rscript -e "IRkernel::installspec()"


## 2. Add a new Dockerfile to root dir

## 3. Edit _config.yml to activate Rocket botton

    launch_buttons:
      notebook_interface: jupyterlab
      colab_url: "https://colab.research.google.com"
      binderhub_url: "https://mybinder.org"
      thebe: true
    
    # Parse and render settings
    # parse:
    #  myst_enable_extensions:  # default extensions to enable in the myst parser. See https://myst-parser.readthedocs.io/en/latest/using/syntax-optional.html
    #    # - amsmath
    #    - colon_fence
    #    # - deflist
    #    - dollarmath
    #    # - html_admonition
    #    - html_image
    #    - linkify
    #    # - replacements
    #    # - smartquotes
    #    - substitution
    #    - tasklist
    
    # Files to exclude from the build
    exclude_patterns: [nlp-enrichment/enrichment_tweaked.ipynb, data-input/aux/*, word_search/parse_conll_make_search.ipynb, README.md, Markdown/R_Markdown.md, Documentation.md]
    
    # Enable interactive widgets
    jupyter:
    widgets:
      enable: true


## 4. First upload R_Lerneinheit.ipynb to notebook dir. Then replace corresponding md to ipynb file in _toc.yml

    - caption: 5. Datenmanipulation
      chapters:
      - file: Markdown/Datenmanipulation
      - file: Markdown/Datenstruktur
      - file: notebook/R_Lerneinheit # Markdown/R_Markdown, replacement here
      - file: notebook/R_Übung_Reprodu # Markdown/22_Übung_Reproduzierbarkeit, replacement here
      - file: notebook/R_Übung_Zeitreihe # Markdown/23_Übung_Zeitreihe, replacement here

# For other details, please read [Documentation](Documentation.md)

    
