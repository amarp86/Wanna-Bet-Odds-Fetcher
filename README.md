# App Title: Wanna_Bet_Odds_Fetcher

[Link to Deployed Site](https://amarp86.github.io/Wanna-Bet-Odds-Fetcher/)

App Description: Web App will fetch current sports bettings odds for upcoming matches per league chosen by user.

API: [Link to API] (https://the-odds-api.com/)

API Snippet: ` [{ "sport_key": "americanfootball_nfl", "sport_nice": "NFL", "teams": ["Chicago Bears","Tampa Bay Buccaneers"], "home_team": "Chicago Bears", "commence_time": "2020-10-09T00:20:00Z", "sites": [{ "site_key": "fanduel", "site_nice": "FanDuel", "last_update": "2020-10-07T09:13:27Z", "odds": {"h2h": [188,-225]} }, { "site_key": "bookmaker", "site_nice": "Bookmaker", "last_update": "2020-10-07T09:16:08Z", "odds": {"h2h": [184,-220]} }, { "site_key": "unibet", "site_nice": "Unibet", "last_update": "2020-10-07T09:14:17Z", "odds": {"h2h": [185,-213]} }, { "site_key": "betrivers", "site_nice": "BetRivers", "last_update": "2020-10-07T09:14:33Z", "odds": {"h2h": [185,-215]} }, { "site_key": "williamhill_us", "site_nice": "William Hill (US)", "last_update": "2020-10-07T09:16:48Z", "odds": {"h2h": [190,-220]} }, { "site_key": "draftkings", "site_nice": "DraftKings", "last_update": "2020-10-07T09:17:42Z", "odds": {"h2h": [185,-215]} }, { "site_key": "betonlineag", "site_nice": "BetOnline.ag", "last_update": "2020-10-07T09:16:50Z", "odds": {"h2h": [190,-222]} }, { "site_key": "lowvig", "site_nice": "LowVig.ag", "last_update": "2020-10-07T09:17:12Z", "odds": {"h2h": [190,-220]} }, { "site_key": "betmgm", "site_nice": "BetMGM", "last_update": "2020-10-07T09:14:05Z", "odds": {"h2h": [190,-227]} }, { "site_key": "mybookieag", "site_nice": "MyBookie.ag", "last_update": "2020-10-07T09:13:03Z", "odds": {"h2h": [190,-240]} }, { "site_key": "betfair", "site_nice": "Betfair", "last_update": "2020-10-07T09:16:05Z", "odds": { "h2h": [200,-208], "h2h_lay": [210,-200] } }, { "site_key": "intertops", "site_nice": "Intertops", "last_update": "2020-10-07T09:13:08Z", "odds": {"h2h": [180,-220]} }, { "site_key": "pointsbetus", "site_nice": "PointsBet (US)", "last_update": "2020-10-07T09:14:44Z", "odds": {"h2h": [180,-225]} }, { "site_key": "gtbets", "site_nice": "GTbets", "last_update": "2020-10-07T09:13:31Z", "odds": {"h2h": [195,-225]} } ], "sites_count": 14 },`

Wireframes: [Link to Wireframe](https://wireframe.cc/SXndMc)

MVP:

1. Establish Connection to API with axios
2. Allow User to select a sports league (NBA, NCAAB, NFL, etc..)
3. Allow user to select a matchup within selected league (NY Knicks vs Dallas Mavericks, Penn State Nittany Lions vs Ohio State Buckeyes, Kansas City Chiefs vs Tampa Bay Buccaneers, etc)
4. Append DOM to display current realtime bettings odds at available US sportsbooks.
5. Manipulate DOM with CSS to display information in a presentable manner.

Post-MVP:

1. Append DOM to link externally to sportsbooks allowing wagers on current matchup that are within API
2. Make second API call to fetch previous results based on odds and display "previous outcomes"
3. Use JS to find sportsbook with BEST ODDS for selected Match-Up and append to DOM.

Changelog:

1. API paywall restricts #1 and #2 of post MVP goals - feature can be updated when API is changed to paid version.
2. Due to API restrictions, instead of selecting an individual team, users must select a matchup between 2 teams.

Schedule and Goals:
| Date | Goal of the Day | Status |
| --------- | --------------------------------------- | ------- |
| 1/25/2021 | Prompt/Wireframe | Complete |
| 1/26/2021 | Approval/Begin Coding | Complete |
| 1/27/2021 | Core App Structure | Complete |
| 1/28/2021 | Initial Deployment | Complete |
| 1/29/2021 | Meet MVP Deliverables | Complete |
| 2/1/2021 | Presentations/Submission | Pending |

Priority Matrix: [Link to Priority Matrix](https://drive.google.com/file/d/1h6b-Pgw7N-GC2XifGAZZEinY6ZF-N-Ef/view?usp=sharing)
![priority matrix](https://github.com/amarp86/Odds_Fetcher/blob/main/Wanna%20Bet%20Priority%20Matrix.png)

Timeframes:
| Component | Priority | Estimate Time | Time Invested | Actual Time |
| ------------------------------- | :------: | :-----------: | :-----------: | :---------: |
| Setting Up Basic Layout | H | 2 Hr | 1.5 Hr | 1.5 Hr |
| Accessing API | H | 3 Hr | 3 Hr | 3 Hr |
| JS API Initial Get Request | H | 3 Hr | 2 Hr | 2 Hr |
| Parsing API Data | H | 3 Hr | 3 Hr | 3 Hr |
| Creating HTML Elements | H | 3 Hr | 2 Hr | 2 Hr |
| JS DOM Odds Appends | H | 3 Hr | 3 Hr | 3 Hr |
| JS DOM Teams Appends | H | 3 Hr | 2 Hr | 2 Hr |
| Clear Screen/Reset Page | M | 3 Hr | 2 Hr | 2 Hr |
| CSS Styling DESKTOP | H | 3 Hr | 3 Hr | 3 Hr |
| CSS Styling MOBILE | H | 3 Hr | 3 Hr | 3 Hr |
| POST MVP - Best Odds | L | 3 Hr | 3 Hr | 3 Hr |
| UI/UX breakpoints | M | 3 Hr | 3 Hr | 3 Hr|
| Testing API call(s) | H | 3 Hr | 2 Hr | 3 Hr |
| Testing CSS breakpoints | M | 3 Hr | 3 Hr | 3 Hr |
| Hosting Final Product | M | 3 Hr | 1 Hr | 3 Hr |
| Total Time | | 44 Hrs | 36.5 | 36.5 Hr |

Code Snippet:

````for (let i = 0; i < game.sites.length; i++) {

        let homeOdds = document.createElement('div')
        homeOdds.setAttribute("class", "home-odds")
        homeOdds.textContent = `${game.teams[0]} : ${game.sites[i].odds.h2h[0]}`;
        let awayOdds = document.createElement('div')
        awayOdds.setAttribute("class", "away-odds")
        awayOdds.textContent = `${game.teams[1]} : ${game.sites[i].odds.h2h[1]}`;
        let bookNames = document.createElement('h3')
        bookNames.setAttribute('class', "booknames")
        bookNames.textContent = game.sites[i].site_nice;

          //all available odds array to get min/max later
        homeArray.push(game.sites[i].odds.h2h[0])
        awayArray.push(game.sites[i].odds.h2h[1])

        appendDiv.append(bookNames)
        appendDiv.append(homeOdds)
        appendDiv.append(awayOdds)
        if (game.sites[i].odds.h2h[2]) {    //checks object arrays for a 3rd index value for draw option
          let drawOdds = document.createElement('div')
          drawOdds.setAttribute('class', "draw-odds")
          drawOdds.textContent = `Draw: ${game.sites[i].odds.h2h[2]}`
          appendDiv.append(drawOdds)
          drawArray.push(game.sites[i].odds.h2h[2]) // if draw exists push value to array for later
        }
      }```


````
