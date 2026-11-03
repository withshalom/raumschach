Raumschach 5×5×5

A browser implementation of Raumschach ("space chess"), the three-dimensional chess variant from early twentieth-century Germany. The board is a 5×5×5 cube, shown as five 5×5 levels labeled α (bottom, White's home) through ε (top, Black's home).

Everything runs in one HTML file with no build step and no dependencies.

Playing

Open index.html in a modern browser. Two modes are available:

	•	Two players: hot-seat play on one device.
	•	vs Computer: choose your color and a difficulty (Easy, Medium, Hard).

Tap or click a piece to see its legal moves, then tap a destination. Undo takes back one move (two in computer mode, so it returns to your turn).

Rules implemented

Piece	Movement
Rook	Any distance along one of the three axes
Bishop	Any distance diagonally within one of the three coordinate planes
Queen	Rook, bishop, and unicorn moves combined
King	One step in any of the 26 directions
Knight	A 2-by-1 leap in any coordinate plane (24 moves from the center)
Unicorn	Any distance diagonally through all three axes at once (8 directions)
Pawn	One step forward or one step straight up a level. Captures diagonally forward, diagonally forward and up, or straight forward and up. No double step.

Pawns promote on the far rank of the two outer levels on each side. The promotion choice includes any piece except the king.

Moves that leave your own king in check are illegal. The game ends on checkmate, stalemate, threefold repetition, 50 moves without a capture or pawn move, or when only kings remain.

Rules not in the reference

Some points were not specified in the source rules and were chosen for this implementation:

	•	No castling.
	•	No en passant.
	•	Pawns on the far rank of the middle levels do not promote.
	•	The computer always promotes to a queen.

The computer opponent

The AI uses negamax search with alpha-beta pruning, quiescence search over captures, iterative deepening, and a time limit per move. Its evaluation counts material, centralization for minor pieces and unicorns, and pawn advancement. Difficulty controls search depth and time: roughly 1, 2, or 3 plies in 0.7, 1.5, or 3 seconds.

The AI is limited by the speed of the browser and is not a strong player.

Files

	•	index.html: the complete game (rules, AI, and interface)
	•	README.md: this file

Known limitations

	•	Hot-seat only. There is no online play yet.
	•	Pieces use Unicode chess symbols, and the unicorn uses the 🦄 emoji. Appearance varies by device and font.
	•	The game state is not saved. Reloading the page starts a new game.
	•	The engine was tested with scripted checks, not a full suite of play-through tests.

Terminology

"Raumschach" is German for "space chess." The rules here follow the reference at chessvariants.com.
