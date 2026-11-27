#CS117 

>[!important] Question 1
>There are three green frogs and three brown frogs arranged on a sequence of seven lily pads.
>
>The green frogs are on the three leftmost lily pads facing right, whilst the brown frogs are on the three rightmost lily pads facing left. The frogs wish to swap places, so that the green frogs are on the three rightmost lily pads and the brown frogs are on the three leftmost lily pads. However, the frogs can only move forward; that is, the green frogs can only move to the right, and the brown frogs can only move to the left. Also, a frog can only move in one of two ways:
>
>- It can hop forward onto an empty, adjacent lily pad if it lies directly in front of the frog.
>  
>- It can perform a larger jump and leap over a single frog of a *different* colour (on an adjacent lily pad) to land on the next lily pad if it is empty.
>  
>How can the frogs carry out this task?
>
>![[frog-pictures.png]]

Let "G" represent a green frog, "B" represent a brown frog, and "\_" represent an empty lily pad. 

| Move | Action            | State    |
| ---- | ----------------- | -------- |
| 0    | start             | GGG_BBB  |
| 1    | G hops 3 $\to$ 4  | GG_GBBB  |
| 2    | B jumps 5 $\to$ 3 | GGBG_BB  |
| 3    | B hops 6 $\to$ 5  | GGBGB_B  |
| 4    | G jumps 4 $\to$ 6 | GGB_BGB  |
| 5    | G jumps 2 $\to$ 4 | G_BGBGB  |
| 6    | G hops 1 $\to$ 2  | \_GBGBGB |
| 7    | B jumps 3 $\to$ 1 | BG_GBGB  |
| 8    | B jumps 5 $\to$ 3 | BGBG_GB  |
| 9    | B jumps 7 $\to$ 5 |          |
| 10   |                   |          |
| 11   |                   |          |
| 12   |                   |          |
| 13   |                   |          |
| 14   |                   |          |
| 15   |                   |          |



