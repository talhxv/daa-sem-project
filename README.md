# DAA Semester Project

The **Game of Life**, also known simply as **Life**, is a [cellular automaton](https://en.wikipedia.org/wiki/Cellular_automaton "Cellular automaton") devised by the British [mathematician](https://en.wikipedia.org/wiki/Mathematician "Mathematician")  [John Horton Conway](https://en.wikipedia.org/wiki/John_Horton_Conway "John Horton Conway") in 1970. It is a [zero-player game](https://en.wikipedia.org/wiki/Zero-player_game "Zero-player game"), meaning that its evolution is determined by its initial state, requiring no further input. One interacts with the Game of Life by creating an initial configuration and observing how it evolves. It is [Turing complete](https://en.wikipedia.org/wiki/Turing_complete "Turing complete") and can simulate a [universal constructor](https://en.wikipedia.org/wiki/Von_Neumann_universal_constructor "Von Neumann universal constructor") or any other [Turing machine](https://en.wikipedia.org/wiki/Turing_machine "Turing machine").


# Rules

1.  Any live cell with fewer than two live neighbours dies, as if by underpopulation.
2.  Any live cell with two or three live neighbours lives on to the next generation.
3.  Any live cell with more than three live neighbours dies, as if by overpopulation.
4.  Any dead cell with exactly three live neighbours becomes a live cell, as if by reproduction.

##  Psuedo code for play() 

```pseudo
algorithim play() 

input: no input required
output: changes the current state to the next state after making changings (if present)
 
    g <- this.state.gridFull
    g2 <- arrayClone(this.state.gridFull)

    for i <- 0 to this.rows - 1 
        for j <- 0 to this.cols - 1 
            count <- 0
            if i > 0 <- count++ if g[i - 1][j]
            if i > 0 and j > 0 <- count++ if g[i - 1][j - 1]
            if i > 0 and j < this.cols - 1 <- count++ if g[i - 1][j + 1]
            if j < this.cols - 1 <- count++ if g[i][j + 1]
            if j > 0 <- count++ if g[i][j - 1]
            if i < this.rows - 1 <- count++ if g[i + 1][j]
            if i < this.rows - 1 and j > 0 <- count++ if g[i + 1][j - 1]
            if i < this.rows - 1 and this.cols - 1 <- count++ if g[i + 1][j + 1]

            if g[i][j] and (count < 2 or count > 3) <- g2[i][j] <- false
            if not g[i][j] and count == 3 <- g2[i][j] <- true
    
    this.setState prev_state <- 
        gridFull <- g2
        generation <- prev_state.generation + 1
```

## Time complexity 

Key function is **nested loops** hence the time complexity is O(n^2)  

## Space complexity

Since a 2d grid is being initialized and used in every state generation, the space complexity is also O(n^2) 

## Framework used for this project

React [html+css+javascript]

## Link to open website: 

[talhxv.github.io/daa-sem-project/](https://talhxv.github.io/daa-sem-project/ "https://talhxv.github.io/daa-sem-project/")
