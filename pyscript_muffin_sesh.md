---
marp: true
theme: gaia
paginate: true
transition: slide
_class: lead
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.jpg')
---

# Publishing model/data-vis apps with pyscript, panel, and github-pages

---

# Motivation

- our team have a few (two?) R Shiny apps
- intended for non-technical users, but have had difficulty in making them accessible

---

# PyScript

 - https://pyscript.net/
 - PyScript lets you create a frontend web application using Python. 
 - Either 
    - embed Python code in HTML
    <py-script> print('Hello World!') </py-script>|
    , or 
    - link to a Python file and the code will run in the browser.
    <py-script src = './main_panel.py'></py-script>
 - developed by Anaconda people


-----

# How does it work?
    
PyScript sits on top of:

 - pyodide: Python ported to ... 
    - WebAssembly: open standard for executing fast binary code in web apps.

 - pyodide packages include:
    - numpy, pandas, scipy, scikit-learn 
    - matplotlib, bokeh, ...
    - and can use any pure Python packages from PyPi
 
 
 ----

 # A proof of concept

  - one of our shiny apps converted to Python, using Panel for widgetty things. https://panel.holoviz.org/
  - https://github.com/Treasury-Analytics-and-Insights/pyscript_experiment

 ---

 # Limitations

- this github free account plus github-pages treament is only suitable for non-sensitive data
- if your app needs to import data from file, you can't just email the html and supporting files to someone, they need to run a local web server.  *For security, web browsers can't access local files without user permission.* There are probably ways around this, but I haven't looked into it.
- pyodide is a large download, so the first time you run the app it takes a while to load.

