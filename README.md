# mdbook-chess

WIP But stick chess games into mdbook

# Usage

Currently the chess boards are specified via a very simple YAML structure. With
5 possible fields:

* load - either "start" for the starting board or a FEN string. If not provided it's default starting board
* save - name to save board under (can be a list)
* moves - list of moves
* overwrite - boolean of whether to overwrite saved version of the board with these moves

So we can create a starting board like:

```chess
load: start
```

Or like:

```chess
# mdbook seems to hate empty code blocks so have at least a blank line
```

Of course if we want to refer to this board later we need to save it. So we can
create a board with a name to refer to it later as so:

```chess
save: our_board
```

We can then load it and apply some moves - this will overwrite it so to do
alternatives can set overwrite to false and start from previous position. We
can also save multiple boards from a point for exploring many different routes:

```chess
load: our_board
save: ["ck-main", "ck-2", "ck-3"]
moves: ["e4", "c6", "d4", "d5"]
``` 

# License and Copyright

All chess SVGs were created by Wikimedia user Cburnett and are CC BY-SA 3.0
licensed. You can find them [here](https://commons.wikimedia.org/wiki/Category:SVG_chess_pieces)
I've edited them to template in a transform and remove the outer tags for
ease of board generation.

All other aspects of this project are currently licensed under the terms of both
the MIT license and the Apache License (Version 2.0). See LICENSE-MIT and
LICENSE-APACHE for more details.
