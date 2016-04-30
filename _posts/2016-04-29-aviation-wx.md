---
layout: post
title: Aviation WX
---

After throwing together my command line tool to fetch METARs and TAFs, I thought it might be nice to make it somewhat RESTful. Using some of the same codebase along with Flask, I was able to do that. Getting started is pretty simple. Most of the requirements are Python modules that every system has. The only exception is Flask, and you can get that with a simple `pip install flask`. 

To get started, check out the repo: `git clone https://github.com/kevin-bowers/avwx.git`

To launch it, just execute the binary; by default it listens on port 5000 (localhost only). From there, the queries are pretty simple:
`/ICAO_CODE` - will return the METAR for the given airport
<br>`ICAO_CODE/TAF` - will return the TAF for the given airport (if a TAF is available for that airport)<br>
Appending `?summary` to the end of either request will return a summary that's more human readable (also great for when you're just learning to read METARs and TAFs)

That's all there is to it. 

I included the readme below.
<hr>

# Aviation Weather
A RESTful way to get METARs and TAFs
## Requirements
- Python 2.7
- Requests
- JSON
- Flask
- SQLite3

## Usage
After launching the app:

- Query `/<ICAO_Code>` for METAR
- Query `/<ICAI_Code>/taf` for TAF
- Append `?summary` for a more human readable result

## Data Sources:
Airport Info - [ourairports.com](ourairports.com)
Weather Info - [avwx.rest](avwx.rest)
