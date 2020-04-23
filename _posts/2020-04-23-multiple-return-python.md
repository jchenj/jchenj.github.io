---
layout: post
title: "Multiple Return Values in Python"
date: 2020-04-23
---

I was working on adding a page to a Flask web app that displays data from the Nasa Astronomy Photo of the Day API. I had added a route successfully that pulled the URL for the current day's photo and sent it to the page:

````python
@app.route('/apod')
def apod():
    photo = get_apod()
    return render_template('apod.html', photo=photo)


def get_apod():
    r = requests.get('https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY')
    data = r.json()
    return data['url']
````

I then wanted to add the photos's description - also provided by the API - to the page. I wondered how I could do this. Did I need to write a separate function to return the description - e.g. `get_description()` - and refactor the initial function to `get_photo()`? Or could I return both the photo URL and description from `get_apod()`? A quick check reminded me that multiple return values are possible in Python, and that I can store these variables at the same time as I call the function:
 
````python
@app.route('/apod')
def apod():
    photo, text = get_apod()
    return render_template('apod.html', photo=photo, text=text)


def get_apod():
    r = requests.get('https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY')
    data = r.json()
    return data['url'], data['explanation']
````
    