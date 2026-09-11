# adult-league-scheduler.html
Package to build divisions and league schedule, standings, playoff bracket, and team stats
**Ice**
Weekly lines repeat on their weekday between their available-from and available-until dates. Every line is either game ice or practice ice, never both, and the two pools never mix. One-off slots can be added for dates outside the pattern. Rink closures remove dates from everything and override every other rule. Any slot nobody uses is listed as open ice rather than quietly dropped.

**Divisions**
Teams only play inside their own division. Divisions never meet, and each crowns its own champion. A division can be limited to certain weekdays, given its own start and end dates, its own game cap, and its own practice count. Ice is shared rather than owned, with one exception: a practice line assigned to a division belongs to it alone. Everything else is allocated by workload, and a division limited to a couple of nights gets a proportionally larger claim on those nights so it isn't crowded out.

**Teams**
A team belongs to one division. Its day buttons set which weekdays it can play, and the blackouts list blocks specific dates. Both are binding — the scheduler works around them rather than flagging them afterwards. Practice count can be set per team, and zero means none.

**Caps**
Each division schedules teams × cap ÷ 2, rounded down. No team is ever scheduled past its cap. When teams × cap is odd, one team finishes a game short rather than one going over. Practices follow the same rule against their own cap.

**Placement**
One game per team per week, Sunday through Saturday. A division never takes more slots in a week than its teams can fill — three for six teams, two for four. When a double week is unavoidable, the two games go on different days with the widest gap available. No team ever plays twice in one day; a game that would require it is left unplaced and flagged instead. Practice slots hold one to four teams, and a line can be reserved for named teams.

**Postseason**
The regular season finishes before any bracket begins. The end of the season is reserved for playoffs before regular games are placed. Each round waits for the previous round to finish. Seeding is by points, then goal difference, within the division.

**Precedence, strongest first**
Rink closures, then division day rules and date windows, then team day rules and blackout dates, then caps, then one game per week, then the different-day rule, then even spread across the season.
