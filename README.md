```
import random

class SportsGame:
    def __init__(self):
        self.football_players = {
            "Goalkeepers": ["Alisson", "Ederson", "David de Gea"],
            "Defenders": ["Virgil van Dijk", "Aymeric Laporte", "Trent Alexander-Arnold"],
            "Midfielders": ["Kevin De Bruyne", "Mohamed Salah", "N'Golo Kante"],
            "Forwards": ["Lionel Messi", "Cristiano Ronaldo", "Robert Lewandowski"]
        }
        
        self.cricket_players = {
            "Batsmen": ["Virat Kohli", "Rohit Sharma", "Steve Smith"],
            "Bowlers": ["Jasprit Bumrah", "Pat Cummins", "Jofra Archer"],
            "All-rounders": ["Ben Stokes", "Ravindra Jadeja", "Mitchell Starc"]
        }
        
        self.football_tournaments = {
            "World Cup": ["Group Stage", "Round of 16", "Quarterfinals", "Semifinals", "Final"],
            "Champions League": ["Group Stage", "Round of 16", "Quarterfinals", "Semifinals", "Final"],
            "Premier League": ["League Stage", "Playoffs"]
        }
        
        self.cricket_tournaments = {
            "ICC World Cup": ["Group Stage", "Semifinals", "Final"],
            "Indian Premier League": ["League Stage", "Playoffs"],
            "Big Bash League": ["League Stage", "Playoffs"]
        }
        
        self.football_teams = {}
        self.cricket_teams = {}
        
        self.football_score = {"Home": 0, "Away": 0}
        self.cricket_score = {"Batting": 0, "Bowling": 0}
        self.cricket_wickets = 0
        self.cricket_overs = 0
        self.football_ball_possession = "Home"

    def create_football_team(self):
        team_name = input("Enter team name: ")
        players = []
        print("Select 11 players:")
        for position in self.football_players:
            print(f"\n{position}:")
            for player in self.football_players[position]:
                print(player)
            player_choice = input("Enter player name: ")
            players.append(player_choice)
        self.football_teams[team_name] = players
        print(f"Team {team_name} created successfully!")

    def create_cricket_team(self):
        team_name = input("Enter team name: ")
        players = []
        print("Select 11 players:")
        for position in self.cricket_players:
            print(f"\n{position}:")
            for player in self.cricket_players[position]:
                print(player)
            player_choice = input("Enter player name: ")
            players.append(player_choice)
        self.cricket_teams[team_name] = players
        print(f"Team {team_name} created successfully!")

    def play_football_match(self, ai=False):
        home_team = "Hussain"
        away_team = "Hussain bin Sabir"
        
        print(f"Football Match: {home_team} vs {away_team}")
        
        for minute in range(90):
            print(f"Minute {minute+1}")
            if ai:
                action = random.choice(["pass", "shoot", "tackle"])
                player = random.choice(self.football_teams[away_team])
                if action == "pass":
                    print(f"{player} from {away_team} passes the ball")
                elif action == "shoot":
                    if random.random() < 0.5:
                        self.football_score["Away"] += 1
                        print(f"{player} from {away_team} scores!")
                    else:
                        print(f"{player} from {away_team} misses!")
                elif action == "tackle":
                    self.football_ball_possession = "Home" if self.football_ball_possession == "Away" else "Away"
                    print(f"Ball possession changed to {self.football_ball_possession} team")
            else:
                action = input("Enter action (pass/shoot/tackle): ")
                player = input("Enter player name: ")
                if action == "pass":
                    print(f"{player} from {home_team} passes the ball")
                elif action == "shoot":
                    if random.random() < 0.5:
                        self.football_score["Home"] += 1
                        print(f"{player} from {home_team} scores!")
                    else:
                        print(f"{player} from {home_team} misses!")
                elif action == "tackle":
                    self.football_ball_possession = "Away" if self.football_ball_possession == "Home" else "Home"
                    print(f"Ball possession
```
