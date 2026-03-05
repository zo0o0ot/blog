+++
title = "2026 Winter Olympics - Fantasy Results"
date = 2026-02-21T00:00:00Z
tags = ["olympics", "charts"]
featured_image = ""
description = "Charts showing 2026 Winter Olympics fantasy performance with hardware counts and handicap multipliers"
+++

The 2026 Milan-Cortina Winter Olympics are in the books. Here's a different way to look at the results, with custom scoring that counts every medal placed around an athlete's neck and handicaps the big nations to keep things competitive.

<!--more-->

## Chart 1: Final Fantasy Standings

The ultimate leaderboard showing handicap-adjusted final scores alongside delegation size. Netherlands (39 athletes) and Norway (80 athletes) at the top despite very different delegation sizes.

{{< obsplot-bar-grouped csv="/data/olympics-2026/country_blog_data.csv" y="Country" field1="Multiplied Hardware" label1="Points" field2="Participants" label2="Athletes" title="Final Fantasy Standings" height="1500" >}}

## Chart 2: Hardware Boost

Shows which countries benefited most from team sports. USA jumps from 33 medals to 96 hardware; Finland from 6 to 36.

{{< obsplot-labeled-dot csv="/data/olympics-2026/country_blog_data.csv" x="Total Medals" y="Total Hardware" label="Country" title="Hardware Boost: Team Sport Impact" height="500" >}}

## Chart 3: The Multiplier Effect

Reveals how handicaps reshuffled the standings. Georgia (8 athletes, 1 medal) rockets up; large delegations get compressed.

{{< obsplot-labeled-dot csv="/data/olympics-2026/country_blog_data.csv" x="Weighted Hardware" y="Multiplied Hardware" label="Country" title="The Multiplier Effect" height="500" >}}

## Chart 4: Bang for Your Buck

Small delegation efficiency - who drafted well? Netherlands (39 athletes) outscoring USA (233 athletes).

{{< obsplot-labeled-dot csv="/data/olympics-2026/country_blog_data.csv" x="Participants" y="Multiplied Hardware" label="Country" title="Bang for Your Buck: Delegation Size vs Final Score" height="500" >}}

## Chart 5: Hardware Leaders

Pure physical medal count before handicaps. Shows the team sport dominance (USA, Canada, Italy, Switzerland).

{{< obsplot csv="/data/olympics-2026/country_blog_data.csv" type="bar" x="Total Hardware" y="Country" title="Hardware Leaders (Medals Around Necks)" height="800" >}}

---

## How the Math Works

This fantasy league uses a custom scoring system designed to level the playing field between winter sports superpowers and smaller nations. Here's how it all breaks down:

### Weighted Medals

Standard Olympic medal counts treat all medals equally. We weight them:

- 🥇 Gold = **3 points**
- 🥈 Silver = **2 points**
- 🥉 Bronze = **1 point**

So a country with 5 🥇, 3 🥈, and 2 🥉 would have: (5×3) + (3×2) + (2×1) = **23 weighted points**.

### Hardware: Medals Around Necks

Here's where it gets interesting. The standard medal count treats a hockey gold the same as a downhill skiing gold. But hockey puts **25 medals** around necks (the whole roster), while skiing awards just **1**.

We count every physical medal awarded:

| Event Type | Hardware per Medal |
|------------|-------------------|
| Ice Hockey | 23-25 |
| Figure Skating Team Event | 8 |
| Luge Team Relay | 6 |
| Short Track Relays | 5 |
| Bobsled (4-person), Cross-Country Relays, Curling | 4 |
| Team Pursuit (Speed Skating) | 3 |
| Pairs, Ice Dance, Doubles, Two-Person Bobsled | 2 |
| Individual Events | 1 |

This is why the USA jumps from 33 medals to 96 hardware, and why Finland's 6 medals become 36 pieces of actual metal.

### Weighted Hardware

Same 3/2/1 weighting, but applied to hardware counts:

**Weighted Hardware** = (Hardware Gold × 3) + (Hardware Silver × 2) + (Hardware Bronze × 1)

### The Draft Handicap (Multiplier)

To make the fantasy draft competitive, larger delegations get penalized. The multiplier is calculated as:

**Multiplier = 233 ÷ Delegation Size**

The USA sent 233 athletes, so their multiplier is exactly **1.0** (no bonus, no penalty). Meanwhile:

- Netherlands (39 athletes): **5.97× multiplier**
- Georgia (8 athletes): **29.13× multiplier**
- Norway (80 athletes): **2.91× multiplier**

This means a small nation's single silver medal can outscore a superpower's medal haul.

### Final Score: Multiplied Hardware

The fantasy standings use:

**Multiplied Hardware = Weighted Hardware × Multiplier**

This rewards drafting efficient small delegations over the obvious powerhouses. The Netherlands finished second overall despite having just 39 athletes, because their speed skating dominance combined with a favorable multiplier.

---

## Country Breakdowns

### Norway 🇳🇴

The Nordic powerhouse rolled into Milan-Cortina with **80** athletes and left no doubt about their winter sports supremacy. Their **41 medal** haul (18 🥇, 12 🥈, 11 🥉) translated to a weighted score of 89 points before any adjustments.

Relay and team event dominance pushed their actual hardware count to **63 medals** draped around Norwegian necks. With their draft multiplier applied, they finished with a commanding **399.01** Multiplied Hardware score.

---

### Netherlands 🇳🇱

The Dutch proved once again that a small, focused squad can dominate. Just **39** athletes brought home **20 medals** (10 🥇, 7 🥈, 3 🥉) for a baseline of 47 weighted points.

Team relays bumped their physical medal count to **26 hardware medals**. Their favorable draft position amplified this into a whopping **376.38** Multiplied Hardware score, nearly catching Norway despite half the delegation size.

---

### United States 🇺🇸

Team USA arrived with the largest contingent: **233** athletes spread across every discipline. They collected **33 medals** (12 🥇, 12 🥈, 9 🥉) for 69 weighted points.

Their dominance in team sports was staggering, inflating their hardware count to **96 actual medals** worn on the podium. However, their draft handicap kept the final Multiplied Hardware score at **249.0**, a reminder that size alone doesn't win fantasy leagues.

---

### Canada 🇨🇦

Our neighbors to the north brought **210** athletes and walked away with **21 medals** (5 🥇, 7 🥈, 9 🥉), good for 38 weighted points.

Hockey, curling, and other team events ballooned their hardware to **86 physical medals**. The draft multiplier brought them to a final score of **183.07** Multiplied Hardware.

---

### Great Britain 🇬🇧

Britain's **55** athletes punched well above their weight, snagging **5 medals** (3 🥇, 1 🥈, 1 🥉) for 12 weighted points.

Relay success tripled their hardware to **15 medals** on British necks. A generous draft handicap rewarded their efficiency with a **160.98** Multiplied Hardware score.

---

### Sweden 🇸🇪

The Swedes sent **110** athletes and delivered **18 medals** (8 🥇, 6 🥈, 4 🥉) worth 40 weighted points.

Team events nearly doubled their count to **32 hardware medals**. Their final Multiplied Hardware score of **150.39** kept them competitive in the fantasy standings.

---

### Italy 🇮🇹

The host nation showed up with **196** athletes and put on a show: **30 medals** (10 🥇, 6 🥈, 14 🥉) for 56 weighted points.

Home-ice advantage in team sports pushed their hardware to **69 physical medals**. Their Multiplied Hardware finished at **143.84**.

---

### France 🇫🇷

France's **162** athletes delivered **23 medals** (8 🥇, 9 🥈, 6 🥉) for 48 weighted points.

Relay prowess elevated their hardware count to **42 medals**. The final Multiplied Hardware score: **138.07**.

---

### Germany 🇩🇪

Germany brought **189** athletes and collected **26 medals** (8 🥇, 10 🥈, 8 🥉), earning 52 weighted points.

Team events doubled their hardware to **56 medals**. They finished with exactly **138.07** Multiplied Hardware, tied with France.

---

### Austria 🇦🇹

The Alpine specialists sent **117** athletes and grabbed **18 medals** (5 🥇, 8 🥈, 5 🥉) for 36 weighted points.

Their hardware count reached **33 medals** through team success. Final Multiplied Hardware: **131.44**.

---

### South Korea 🇰🇷

South Korea's **71** athletes secured **10 medals** (3 🥇, 4 🥈, 3 🥉) worth 20 weighted points.

Relay events pushed their hardware to **18 medals**. A solid draft position lifted them to **131.27** Multiplied Hardware.

---

### Switzerland 🇨🇭

The Swiss contingent of **175** athletes brought home **23 medals** (6 🥇, 9 🥈, 8 🥉) for 44 weighted points.

Team sports inflated their count to **62 hardware medals**. Final score: **126.49** Multiplied Hardware.

---

### Japan 🇯🇵

Japan's **120** athletes claimed **24 medals** (5 🥇, 7 🥈, 12 🥉) for 41 weighted points. That bronze count is impressive depth.

Team events added hardware, bringing them to **37 physical medals**. Their Multiplied Hardware finished at **122.33**.

---

### Georgia 🇬🇪

A tiny squad of just **8** athletes brought home a single silver medal (0 🥇, 1 🥈, 0 🥉) for 2 weighted points.

Here's where fantasy magic happens: their relay doubled the hardware to **2 medals**, and their massive draft handicap rocketed them to **116.5** Multiplied Hardware. Drafting Georgia paid off big time.

---

### Slovenia 🇸🇮

Slovenia's compact **37**-athlete squad earned **4 medals** (2 🥇, 1 🥈, 1 🥉) for 9 weighted points.

Team events brought them to **7 hardware medals**. Their draft multiplier delivered a **113.35** Multiplied Hardware score.

---

### Spain 🇪🇸

Not traditionally a winter sports power, Spain's **20** athletes grabbed **3 medals** (1 🥇, 0 🥈, 2 🥉) for 5 weighted points.

Relay participation pushed hardware to **6 medals**. A favorable draft spot meant **93.2** Multiplied Hardware.

---

### Finland 🇫🇮

Finland brought **103** athletes but struggled on the individual podium: just **6 medals** (0 🥇, 1 🥈, 5 🥉) for 7 weighted points. No golds hurt.

However, team sports transformed their games, ballooning hardware to **36 physical medals**. Final Multiplied Hardware: **90.49**.

---

### New Zealand 🇳🇿

The Kiwis sent only **17** athletes and collected **3 medals** (0 🥇, 2 🥈, 1 🥉) for 5 weighted points.

All individual events meant no hardware boost, staying at **3 medals**. Their draft handicap lifted them to **68.53** Multiplied Hardware.

---

### China 🇨🇳

China's **126** athletes earned **15 medals** (5 🥇, 4 🥈, 6 🥉) for 29 weighted points.

Relay success added some hardware, reaching **20 physical medals**. Final Multiplied Hardware: **62.87**.

---

### Australia 🇦🇺

Australia's **54** winter athletes grabbed **6 medals** (3 🥇, 2 🥈, 1 🥉) for 14 weighted points. Three golds from a nation known for beaches is impressive.

All individual events kept hardware at **6 medals**. Multiplied Hardware: **60.41**.

---

### Poland 🇵🇱

Poland sent **60** athletes and collected **4 medals** (0 🥇, 3 🥈, 1 🥉) for 7 weighted points. The lack of gold stung.

Team relays brought hardware to **7 medals**. Final score: **50.48** Multiplied Hardware.

---

### Brazil 🇧🇷

The true Cinderella story of these games. Brazil's **15** athletes made history, capturing the nation's first-ever Winter Olympics medal, and it was gold (1 🥇, 0 🥈, 0 🥉) worth 3 weighted points.

No team events meant **1 hardware medal**, but who cares? Brazil finally has winter hardware. Their draft handicap delivered **46.6** Multiplied Hardware.

---

### Belgium 🇧🇪

Belgium's **30** athletes secured **1 medal** (0 🥇, 0 🥈, 1 🥉) for a single weighted point.

Team relay success quintupled their hardware to **5 medals**. Draft math brought them to **38.83** Multiplied Hardware.

---

### Individual Neutral Athletes

A delegation of **20** athletes competing without a flag earned **1 medal** (0 🥇, 1 🥈, 0 🥉) for 2 weighted points.

Individual events only meant **1 hardware medal**. Multiplied Hardware: **23.3**.

---

### Bulgaria 🇧🇬

Bulgaria's **20** athletes collected **2 medals** (0 🥇, 0 🥈, 2 🥉) for 2 weighted points.

All individual events kept hardware at **2 medals**. Final Multiplied Hardware: **23.3**.

---

### Czech Republic 🇨🇿

The Czechs brought **114** athletes, their largest winter delegation, and earned **5 medals** (2 🥇, 2 🥈, 1 🥉) for 11 weighted points.

Individual-only medals meant **5 hardware**. Their draft handicap actually compressed them to just **22.48** Multiplied Hardware, a reminder that big delegations face steep fantasy penalties.

---

### Kazakhstan 🇰🇿

Kazakhstan's **36** athletes brought home **1 medal** (1 🥇, 0 🥈, 0 🥉) worth 3 weighted points. One gold is better than none.

Individual event meant **1 hardware medal**. Final score: **19.42** Multiplied Hardware.

---

### Estonia 🇪🇪

Estonia sent **32** athletes and earned **1 medal** (0 🥇, 1 🥈, 0 🥉) for 2 weighted points.

Individual event kept them at **1 hardware medal**. Multiplied Hardware: **14.56**.

---

### Denmark 🇩🇰

Denmark's **39** athletes secured **1 medal** (0 🥇, 1 🥈, 0 🥉) for 2 weighted points.

No team events meant **1 hardware medal**. Final Multiplied Hardware: **11.95**.

---

### Latvia 🇱🇻

Latvia rounded out the medal-winning nations with **68** athletes earning **2 medals** (0 🥇, 1 🥈, 1 🥉) for 3 weighted points.

Individual events only meant **2 hardware medals**. Their Multiplied Hardware finished at **10.28**.
