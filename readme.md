
---
# Cricbuzz Web Scraper

## Hi, Welcome to Cricbuzz Web Scraper Documentation.

- ### Scrape Cricket Data from [Cricbuzz](https://cricbuzz.com/)

- ### Scrape Live, Upcoming, Past Matches, Series, Teams and more

## Import `Cricbuzz` class from `scrape_up.cricbuzz` module.

```python
from cricbuzz import Cricbuzz
```

## Create an instance of `Cricubzz` class.

```python
	cricbuzz = Cricubzz()
```

## Available Methods

| Methods              | Details                                                               |
| -------------------- | --------------------------------------------------------------------- |
| `.get_live_matches()`    | Returns a list of live matches from Cricbuzz.           |
| `.get_recent_matches()`      | Returns a list of recent matches from Cricbuzz.    |
| `.get_upcoming_matches()`    | Returns a list of upcoming matches from Cricbuzz. |
| `.get_series()`   | Returns a dictionary of series in month and year format from Cricbuzz.      |
| `.get_series_from_archive()`   | Returns a list of series from archive from Cricbuzz.      |
| `.get_matches_by_day()`   | Returns a dictionary of matches by day from Cricbuzz.      |
| `.get_series_matches()`   | Returns a list of matches in a series from Cricbuzz.      |
| `.get_series_stats()`   | Returns a list of stats of players in a series from Cricbuzz.      |
| `.get_teams_list()`   | Returns a list of teams from Cricbuzz.      |
| `.get_team_schedule()`   | Returns a list of matches of a team from Cricbuzz.      |
| `.get_team_players()`   | Returns a list of players of a team from Cricbuzz.      |
| `.get_team_results()`   | Returns a list of past results of a team from Cricbuzz.      |
| `.get_team_stats()`   | Returns a list of player stats of a team from Cricbuzz.      |


# Examples -

  ## Get Live Matches
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      live_matches = cricbuzz.get_live_matches(type="international")
      for match in live_matches:
          print(match["match_name"], end="\t")
          print(match["status"])
  ```
  ### Output - 
  ```text
      {match_name}    {match_status}
      {match_name}    {match_status}
      {match_name}    {match_status}....
  ```

  ## Get Recent Matches
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      recent_matches = cricbuzz.get_recent_matches(type="international")
      for match in recent_matches:
          print(match["match_name"], end="\t")
          print(match["status"])
  ```
  ### Output -
  ```text
      {match_name}    {match_status}
      {match_name}    {match_status}
      {match_name}    {match_status}....
  ```
  ## Get Upcoming Matches
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      upcoming_matches = cricbuzz.get_upcoming_matches(type="international")
      for match in upcoming_matches:
          print(match["match_name"], end="\t")
          print(match["status"])
  ```
  ### Output -
  ```text
      {match_name}    {match_status}
      {match_name}    {match_status}
      {match_name}    {match_status}....
  ```

  ## Get Series
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      cric_series = cricbuzz.get_series(type="international")
      for series in cric_series:
          print(series)
          for matches in cric_series[series]:
              print("\t", matches["series_name"], end="\t")
              print("\t", matches["series_dates"])
  ```
  ### Output -
  ```text
      {month} {year}
          {series_name}    {series_dates}
          {series_name}    {series_dates} ....
      {month} {year}
          {series_name}    {series_dates}
          {series_name}    {series_dates} ....
      {month} {year}....
  ```

  ## Get Series From Archive
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      cric_series = cricbuzz.get_series_from_archive(year=2023, type="international")
      for series in cric_series:
          print(series["series_name"], end="\t")
          print(series["series_dates"])
  ```
  ### Output -
  ```text
      {series_name}    {series_dates}
      {series_name}    {series_dates} ....
      {series_name}    {series_dates} ....
  ```

  ## Get Match By Day
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      cric_series = cricbuzz.get_matches_by_day(type="international")
      for day in cric_series:
          print(day)
          for match in cric_series[day]:
              print("\t", match["match_name"], end="\t")
              print("\t", match["start_date_time"])
  ```
  ### Output -
  ```text
      {day}
          {match_name}    {start_date_time}
          {match_name}    {start_date_time} ....
      {day}
          {match_name}    {start_date_time}
          {match_name}    {start_date_time} ....
      {day}....
  ```

  ## Get Series Matches
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      cric_series_matches = cricbuzz.get_series_matches(6351)
      for match in cric_series_matches:
          print(match["match_title"])
  ```
  ### Output -
  ```text
      {match_title}
      {match_title}
      {match_title}....
  ```

  ## Get Series Stats
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      player_stats = cricbuzz.get_series_stats(6351)
      for player in player_stats:
          print(player["Player"], end="\t")
          print(player["Runs"])
  ```
### Output -
  ```text
      {Player_Name}    {Runs}
      {Player_Name}    {Runs}
      {Player_Name}    {Runs}....
  ```

  ## Get Teams List
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      teams = cricbuzz.get_teams_list(type="international")
      for team in teams:
          print(team["team_name"], end="-")
          print(team["team_code"])
  ```
  ### Output - 
  ```text
      {team_name}-{team_code}
      {team_name}-{team_code}
      {team_name}-{team_code}....
  ```
  
  ## Get Team Schedule
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      team_schedule = cricbuzz.get_team_schedule(2)
      for match in team_schedule:
          print(match["match_title"])
  ```
  ### Output -
  ```text
      {match_title}
      {match_title}
      {match_title}....
  ```

  ## Get Team Players
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      team_players = cricbuzz.get_team_players(2)
      for player in team_players:
          print(player["player_name"])
  ```
  ### Output -
  ```text
      {player_name}
      {player_name}
      {player_name}....
  ```

  ## Get Team Results
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      team_results = cricbuzz.get_team_results(2)
      for result in team_results:
          print(result["match_status"])
  ```
  ### Output - \n
  ```text
      {match_status}
      {match_status}
      {match_status}....
  ```

  # Get Team Results
  ```python
      from scrape_up.cricbuzz import Cricbuzz
      cricbuzz = Cricbuzz()
      team_stats = cricbuzz.get_team_stats(2)
      for player in team_stats:
          print("PLAYER NAME", player["PLAYER"])
          print("PLAYER RUNS", player["RUNS"])
          print("PLAYER MATCHES", player["MATCHES"])
          print("\n\n")
  ```
  ### Output - \n
  ```text
      PLAYER NAME   {Player_Name}
      PLAYER RUNS   {Runs}
      PLAYER MATCHES   {Matches}



      PLAYER NAME   {Player_Name}
      PLAYER RUNS   {Runs}
      PLAYER MATCHES   {Matches}


      PLAYER NAME   {Player_Name}
      PLAYER RUNS   {Runs}
      PLAYER MATCHES   {Matches}...
  ```
---