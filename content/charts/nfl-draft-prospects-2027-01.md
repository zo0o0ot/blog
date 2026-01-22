+++
title = "2027 Draft Prospects as of January 21"
date = 2026-01-21T00:00:00Z
tags = ["draft", "charts", "prospects"]
featured_image = ""
description = "Interactive charts showing 2027 NFL Draft prospect data by school, state, conference, and position"
+++

It's never too early to start looking ahead! Here are the first rankings for the 2027 NFL Draft class.

<!--more-->

Honestly, it may potentially be too early for any of these sorts of ranks, but it's interesting to see where the players who have decided to return are being placed in the new draft. Dante Moore is an interesting case, as he probably would have been a top 3 pick in the 2026 draft.

Here are the interactive charts visualizing 2027 NFL Draft prospect data. Hover over chart segments to see detailed information.

## Player Value by School

This chart shows individual players as segments within each school's bar. Each segment represents one player, and you can hover to see player details.

{{< obsplot-stacked csv="/data/2027/2026-01-21/2026-01-21-ranks.csv" groupBy="School" value="Points" color="Conference" title="Player Value by School" height="3000" >}}

## Player Value by State

This chart shows states with individual players as segments, colored by conference. Hover to see player name and school.

{{< obsplot-stacked csv="/data/2027/2026-01-21/2026-01-21-ranks.csv" groupBy="State" value="Points" color="Conference" title="Player Value by State" height="2000" >}}

## Schools by Conference (Stacked)

This chart shows conferences with individual schools as segments. Hover to see school details.

{{< obsplot-stacked csv="/data/2027/2026-01-21/2026-01-21-top-schools.csv" groupBy="Conference" value="ProjectedPoints" color="Conference" title="School Value by Conference" height="800" >}}

## Position Distribution by Conference

This chart shows how draft value is distributed across position groups for each conference.

{{< obsplot-stacked-auto csv="/data/2027/2026-01-21/2026-01-21-ranks.csv" groupBy="Conference" value="Points" color="Position" title="Position Distribution by Conference" height="1200" >}}

## Methodology

The rough methodology used for the Leagify charts is this: Each prospect is given a point value based on their current rank, which is given regardless of position ("Big Board" style).

**Rank values:**

* 01 - 10   : 35 points
* 11 - 25   : 30 points
* 26 - 35   : 25 points
* 36 - 59   : 20 points
* 60 - 70   : 15 points
* 71 - 100  : 10 points
* 101 - 120 : 8 points
* 121 - 150 : 7 points
* 151 - 180 : 6 points
* 181 - 250 : 5 points
* 251 - 300 : 2 points
* 301 - 500 : 1 point

These big board rankings came from [NFL Mock Draft Database 2027 Consensus Big Board](https://www.nflmockdraftdatabase.com/big-boards/2027/consensus-big-board-2027). The most current rankings are from January 21, 2026. Only the value of the player's primary position was considered.

The data is scraped, cleaned, and mushed together with a variety of code, which is available [here](https://github.com/Leagify/prospect-scraper-mddb-2022) for viewing, if you're into that sort of thing.
