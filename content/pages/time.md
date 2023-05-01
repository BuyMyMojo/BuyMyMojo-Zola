+++
title = "Time"
slug = "time"
description = "A bunch of time zones I need all in one"
path = "time-page"
date = "2023-04-05"
weight = 0

[taxonomies]
tags = ["time"]
+++

## Why?

This is just a bunch of different times I need with some extra info I like :)

<script src="//widget.time.is/en_gb.js"></script>
<script>
time_is_widget.init(
    {
        UTC_za00:{template:"TIME<br>DATE", date_format:"dayname, dnum monthname, year, week"},
        Melbourne_z609:{template:"TIME<br>DATE<br>SUN", date_format:"dayname, dnum monthname, year, week", sun_format:"Sunrise: srhour:srminute Sunset: sshour:ssminute<br>Day length: dlhoursh dlminutesm", coords:"-37.8140000,144.9633200"},
        Toronto_z18a:{template:"TIME<br>DATE<br>SUN", date_format:"dayname, dnum monthname, year, week", sun_format:"Sunrise: srhour:srminute Sunset: sshour:ssminute<br>Day length: dlhoursh dlminutesm", coords:"43.7001100,-79.4163000"},
        Berlin_z704:{template:"TIME<br>DATE<br>SUN", date_format:"dayname, dnum monthname, year, week", sun_format:"Sunrise: srhour:srminute Sunset: sshour:ssminute<br>Day length: dlhoursh dlminutesm", coords:"52.5243700,13.4105300"},
        EST_z113:{template:"TIME<br>DATE<br>SUN", date_format:"dayname, dnum monthname, year, week", sun_format:"Sunrise: srhour:srminute Sunset: sshour:ssminute<br>Day length: dlhoursh dlminutesm", coords:"0.0000000,-75.0000000"}
    });
</script>

<!-- Time below here!! -->

<a href="https://time.is/UTC" id="time_is_link" rel="nofollow" style="font-size:36px">Time in UTC (-10):</a>
<span id="UTC_za00" style="font-size:36px"></span>

<br />

<a href="https://time.is/Melbourne" id="time_is_link" rel="nofollow" style="font-size:36px">Time in Melbourne (+0):</a>
<span id="Melbourne_z609" style="font-size:36px"></span>

<br />

<a href="https://time.is/Toronto" id="time_is_link" rel="nofollow" style="font-size:36px">Time in Toronto (-14 EST/-15 EDT):</a>
<span id="Toronto_z18a" style="font-size:36px"></span>

<br />

<a href="https://time.is/EST" id="time_is_link" rel="nofollow" style="font-size:36px">Time in Eastern Standard Time (-14):</a>
<span id="EST_z113" style="font-size:36px"></span>

<br />

<a href="https://time.is/Berlin" id="time_is_link" rel="nofollow" style="font-size:36px">Time in Berlin (-8):</a>
<span id="Berlin_z704" style="font-size:36px"></span>
