>[!important] Question 1

You are given three water jugs, one with a capacity of 8 litres, one with a capacity of 5 litres, and one with a capacity of 3 litres. The 8-litre jug is full (i.e., contains 8 litres of water), the other two are empty. Your goal is to have two jugs containing exactly 4 litres of water. The only kind of action you can take is to pour water from one jug into another jug until the first jug is empty or the second jug is full. For example, in the initial state you can pour water from the 8-litre jug into the 5-litre jug, so that the 8-litre jug contains 3 litres of water, the 5-litre jug contains 5 litres of water, and the 3-litre jug is empty. Alternatively (starting from the initial state again), you can pour water from the 8-litre jug to the 3-litre jug, so that the 8-litre jug contains 5 litres of water, the 3-litre jug contains 3 litres of water, and the 5-litre jug is empty. These are the only two actions you can take initially (or at least the only ones that will change the state, if you consider pouring an empty jug into another jug an admissible action that does nothing).

The possible actions can be encoded by a two-digit **operation code**

- 83 means "pour water from the 8-litre jug into the 3-litre jug"
- 38 means "pour water from the 3-litre jug into the 8-litre jug"
- 53 means "pour water from the 5-litre jug into the 3-litre jug"
- etc.

A 2n-digit decimal number containing only the digits 3, 5, and 8 then codes a sequence of actions when we read the sequence as a sequence of operation codes from left to right. For example, the number 855338 codes the action "first pour water from the 8-litre jug to the 5-litre jug, then from the 5-litre jug to the 3-litre jug, then from the 3-litre jug to the 8-litre jug".

Give the number that corresponds to the shortest sequence of actions that turns the initial state of the problem above (the 8-litre jug is filled with 8 litres of water, the other two jugs are empty) into the desired end state (two jugs cotain exactly 4 litres of water).

- Jug 1 - 8 litres
- Jug 2 - 5 litres
- Jug 3 - 3 litres

Jug 1 is full. 


| Step | Code | Action                  | State (8L, 5L, 3L) |
| ---- | ---- | ----------------------- | ------------------ |
| 0    | -    | -                       | (8, 0, 0)          |
| 1    | 85   | pour 8L jug into 5L jug | (3, 5, 0)          |
| 2    | 53   | pour 5L jug into 3L jug | (3, 2, 3)          |
| 3    | 38   | pour 3L jug into 8L jug | (6, 2, 0)          |
| 4    | 53   | pour 5L jug into 3L jug | (6, 0, 2)          |
| 5    | 85   | pour 8L jug into        |                    |
