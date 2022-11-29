+++
title = "Making an API in Go"
description = "Making an API in go is surpisingly easy"

updated = "2022-11-29"
date = "2021-12-13"
slug = "making-an-api-in-go"
draft = false

[taxonomies]
tags = ["learning", "open-source", "golang"]
+++

## Update! 2022-11-29

I am now a lot more into rust than go so I haven't explored this topic any further.
Making an API in rust is actually pretty sweet and I might revisit this topic in rust.

<h1 class="post-title"></h1>
<sub>Fun thing: to get this line seperating I had to write it as 

```html
<h1 class="post-title"></h1></code>
```
</sub>

## Why make an API?

In my case it's to log the temp of my pool.
Me and my old man have been working on custom pool heating and we wanted to automate it a little.

I've been working on an arduino to measure the temp and to automatically shut off the heat pump when it is at X temp or it is X-PM in the arvo.

The arduino I'm using has an ESP 8266 wifi chip, so I'm gonna use that to access the API.

## How?

I made the API in go so it could be light wight and ultra performant!

It has two very simple functions;

### Log temp to a CSV

By going to `http://localhost:8080/log/{temp}` it saves whatever is after `log/` as the temp along with the current time and date inside of a CSV file

### Display all entries inside the CSV as a HTML table

By going to `http://localhost:8080/list/` it simple displays all entries as a table for easy checking

{{ image(src="/img/screencaps/Screenshot-20211213141012-363x268/Screenshot-20211213141012-363x268.webp", alt="List of all temps",
         position="center", style="border-radius: 8px; width: 50%;") }}

## Tech

It's actually extremely simple;

### /log/

using the [mux](https://github.com/gorilla/mux) http routing library I can easily get the temp variable just by listening to `/log/{temp}` 

```go
    // create a new instance of a mux router
	r := mux.NewRouter()

	// treat anything after /log/ as the temp variable and call handleTemp
	r.HandleFunc("/log/{temp}", handleTemp)
```

the `handleTemp` function simply returns `200 OK` to the user and calls aother function

```go
    func handleTemp(w http.ResponseWriter, r *http.Request) {
	    // read temp from request
	    vars := mux.Vars(r)

	    // reply with 200 OK
	    w.WriteHeader(http.StatusOK)

	    // log temp
	    logTemp(vars["temp"])
    }
```

`logTemp` only does a couple of things, it generates the date and time and then creates an entry in the csv file

```go
    // Get current date and time
	dt := time.Now()

    // Create new record
	csvTitles := []string{dt.Format("01-02-2006 15:04:05"), temp}

	// Append record to CSV
	if err := w.Write(csvTitles); err != nil {
		log.Fatalln("error writing record to file", err)
	}
```

### /list/

When you go to `/list/` it just lists through the CSV and quickly generates some basic HTML

```go
    htmlResponse := "<html><head><style>table, th, td {\n  border: 1px solid black;\n}</style></head><body><table><tr><th>Date</th><th>Temperature</th></tr>"

	for _, record := range records[1:] {
		htmlResponse += "<tr><td>" + record[0] + "</td><td>" + record[1] + "</td></tr>"
	}

	htmlResponse += "</table></body></html>"
```

## Conclusion

Writing a super basic API/Website in go is actually super easy! This was an enjoyable learning experince and went super smoothly.

I'm excited to learn more about Go APIs in the future!
