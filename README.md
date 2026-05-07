# Chess-position-analysis-results
This is a project to find positionally interesting chess positions that can be used for puzzles. The idea is that there are loads of resources for tactical puzzles, but not as many for positional puzzles.

# Using this work
You are free to do what you like with this work, but if you could link back / credit this repository and contributors (see below) that would be great.

# Credits
* WIM/FM Liwia Jarocka
* WGM Michalina Rudzińska
* WGM Margarita Voyska
* Vlad Ghita for his work on exploring the data with machine learning in mind
* 'Fiddler' for his guidance

# Overview
I have mined the Lichess games database for positions which could possibly be used as positional, rather than tactical, puzzles. I've done this by looking for positions with non-tactical moves that give a clear - but not massive - advantage over the second best move.

I then I asked some strong players (see above) to review each position and choose only the ones that satisfied the question "Is this position a puzzle with a single, constructive answer", and to assign to one or more categories (these categories were suggested by the players)

* Initiative
* Piece Development
* Endgame Technique
* Gaining Space
* Trading / Exchanging
* Prophylaxis
* Piece Co-ordination
* Exploiting a Weakness
* King Safety
* Restricting Opponent's Pieces
* Fixing the Pawn Structure
* Controlling the Centre
* Other

I also asked them to assign each puzzle a difficulty level:

1 - Easy (1200 - 1500 Elo)

2 - Moderate (1500 - 1800 Elo)

3 - Hard (1800 - - 2000 Elo)

4 - Very Hard (2000+ Elo)


# Output
There are two sets of output:

## PGN
The PGN files contain custom headers for the themes and difficulty. You can load them in any chess app / site.

## CSV
CSV files with the positions, best move, and categories

# Small plug
Looking for a place to play high quality, classical games of chess? Check out [Lichess Ladders](https://lichessladders.com)

# Future work
At some point I will put the puzzles on [Chess Gubbins](https://chessgubbins.com). If there is interest, I will source more positions too.

# Feedback
The classification was done by humans, so is obviously subjective. If there are puzzles that you feel are incorrectly classified then feel free to raise an issue.

