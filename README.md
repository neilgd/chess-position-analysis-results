# Chess-position-analysis-results
This is a project to find thousands of positionally interesting chess positions that can be used for puzzles

# Using this work
You are free to do what you like with this work, but if you could link back / credit this repository and contributors (see below) that would be great.

# Credits
* WIM/FM Liwia Jarocka
* WGM Michalina Rudzińska
* WGM Margaria Voyska
* 'Fiddler' for his guidance

# Iverview
I have mined the Lichess games database for positions which could possibly be used as positional, rather than tactical, puzzles. I've done this by looking for positions with non-tactical moves that give a clear - but not massive - advantage over the second best move.

I then I asked some strong players (see above) to review each position and answer the question "Is this position a puzzle with a single, constructive answer", and to assign to one or more categories (these categories were suggested by the players)

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


# output
There are two sets of output:

## PGN
The PGN files contain only the positions marked as useful by the (human) classifers. They also contain custom headers for the themes and difficulty.

## CSV
The CSV files contain all the positions that were mined and classified, even if they were judged **not** to be useful. They also contain a lot of extra information, in the hope that somebody smarter than I am will be able to build an automatic position classifier at some point.

In particular, I have passed all the positions through [Ethereal](https://github.com/AndyGrant/Ethereal)'s evaluation function and exposed its *internal* valuation parameters. Its evaluation function considers *human-ish* concepts such as king safety, pawn structure etc., and exposes them as centipawn values. Note that I have included the result *just for the position considered*. There is no search, or recursiveness or anything deeper than a single snapshot of Ethereal's hand-crafted evaluation function.

I have included the following parameters for both black and white, for both before and after, the best move in each position. Note that Ethereal's concepts don't necessarily correspond to human ones.

### For the overall position (before and after the move)
* final_eval - Ethereal's overall valuation of the position, from white's perspective, in centipawns
* psqtmat - An indication of the total imbalance of material, based on its position (eg a Knight on the edge is worth less than one in the centre; a rook in the endgame is worth more than in the middle game)
* material_imbalance - The *material* component of PsqtMat
* position_imbalance - The *positional* component of PsqtMat
* closedness - How closed a position is
* complexity - How complex a position is, weighted towards the end game

#### The centre
There are two centres - the small centre (4 squares) and big centre (16 squares). Each positition has scores for each centre, before and after the move:

* white - squares controlled by white
* black - controlled by black
* contested - contested squares
* uncontrolled - uncontrolled

The importance of the centre changes depending on the stage of the game (middle game or end game)

### For each colour (before and after the move)
* pawns - How strong the side's pawns are, in centipawns, from the side's perspective
* pawns_and_king_safety_without_king_and_pawns - The pawn and king contribution to king *safety*, before pawn storms and pawn shelters are taken into account
* pawns_and_king_safety_with_king_and_pawns - The pawn and king contribution to king *safety*, once pawn storms and pawn shelters are taken into account
* pawns_and_king_evaluation_without_king_and_pawns - The pawn and king contribution to king *evaluation*, before pawn storms and pawn shelters are taken into account
* pawns_and_king_evaluation_with_king_and_pawns - The pawn and king contribution to king *evaluation*, once pawn storms and pawn shelters are taken into account
* knights - Strength of knighs
* bishops - Of bishops
* rooks - Of rooks
* queens - Of queens
* kings - of Kings
* passed - strength of passed pawns
* threats - measure of threats posed
* space - a measure how much the side is restricting the opponent
* safe_space - not from Ethereal, but a count of the spaces behind your own pawns you control


# Notes
Note that the 'Controlling the Centre' category was included relatively recently so may not be accurately populated for the earlier puzzles

