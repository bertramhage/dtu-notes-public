## Games and Strategic thinking

##### Order
**Simultaneous-move game**: Game in which each player makes decisions without the knowledge of the other players' decisions.

**Sequential-move game**: Game in which one player makes a move after observing the other player's move

##### Frequency
**One shot game**: Game in which players interact to make decisions only once

**Repeated game**: Game in which players interact to make decisions more than once

## Simultaneous-Move, One-shot Games

> **Normal-form game**
> A representation of a game indicating the players, their possible strategies, and the payoffs resultning from alternative strategies.

![[Skærmbillede 2023-12-16 kl. 21.21.31.png]]
**Dominant strategy**: A strategy that results in the highest payoff to a player regardless of the opponent's action
(Player A has dominant strategy Up, Player B has no dominant strategy)

**Secure strategy**: A strategy that guarantees the highest payoff given the worst possible scenario.
(Player A has secure strategy Up guaranteeing at least $10,
Player B has secure strategy Right guaranteeing at least $8)

**Nash equilibrium strategy**: A condition describing a set of strategies in which no player can improve her payoff by unilaterally changing her own strategy, given the other players' strategies.
(Equilibrium results when Player A plays Up and Player B plays Left)

>[!example]+ Monitoring Employees
>![[Skærmbillede 2023-12-16 kl. 21.30.01.png]]
>Q: How should the agents play this type of game?
>A: Play a mixed (randomized) strategy, whereby a player   randomizes over two or more available actions in order to keep rivals from being able to predict his or her actions.

>[!example]+ Nash Bargaining
>![[Skærmbillede 2023-12-16 kl. 21.31.27.png]]
>There three Nash equilibrium outcomes associated with this game:  
>Equilibrium strategy 1: Management chooses 100, union chooses 0  
>Equilibrium strategy 2: Both players choose 50  
>Equilibrium strategy 3: Management chooses 0, Union chooses 100

## Infinitely Repeated Games

> An infinitely repeated game is a game that is played over and over again forever, and in which players receive payoffs during each play of the game.

Recall present value when a firm earns the same profit $\pi$
$$
PV_{Firm}=\left( \frac{1+i}{i} \right)\pi
$$
##### Trigger strategy

> Strategy that is contingent on the past play of a game and in which some particular past action “triggers” a different action by a player.

>[!example]+ Trigger strategy example: Supporting Collusion with Trigger Strategies
>![[Skærmbillede 2023-12-16 kl. 21.35.56.png]]
>Both firms charge the high price, provided neither of them has ever "cheated" in the past. If one firm cheats the other player will punish the deviator by charging the low price forever after.

>[!info] Sustaining Cooperative Outcomes with Trigger Strategies
>Consider a infinitely repeated one-shot game with interest rate $i$. Denote the cooperative one-shot payoff to a player as $\pi^{Coop}$, the maximum one-shot payoff if the player cheats as $\pi^{Cheat}$ and the one-shot Nash equilibrium payoff as $\pi^N$. Assume that
>$$
> \frac{\pi^{Cheat}-\pi^{Coop}}{\pi^{Coop}-\pi^N}≤ \frac{1}{i}.
>$$
>Then the cooperative (collusive) outcome can be  sustained in the infinitely repeated game with the  following trigger strategy: “Cooperate provided that no  player has ever cheated in the past. If any player cheats,  “punish” the player by choosing the one-shot Nash equilibrium strategy forever after. 

>[!example]+ Supporting Collusion with Trigger Strategies
>![[Skærmbillede 2023-12-16 kl. 21.46.35.png]]
>Suppose firm A and B repeatedly play the game above, and the interest rate is 40 percent. Firms agree to charge a high price in each period, provided neither has cheated in the past.
>Q: What are firm A's profit if it cheats on the collusive agreement?
>A: If firm B lives up to the collusive agreement but firm A cheats, firm A will earn $50 today and zero forever after.
>
>Q: What are firm A's profits if it does not cheat on the collusive agreement?
>A: $10+\frac{10}{(1+0.4)}+\frac{10}{(1+0.4)^2}+\dots=\frac{10(1+0.4)}{0.4}=\$35$.
>
>Q: Does an equilibrium result where the firm charge the high price in each period?
>A: Since $50>$35, the present value of firm A's profits are higher if A cheats on the collusive agreement. In equilibrium both firms will charge low price and earn zero profit each period.

##### Factors affecting collusion in pricing games
- Number of firms in the market
- Firm size
- History of the market
- Punishment mechanisms

## Finitely repeated games

>Games in which a one-shot game is repeated a finite number of times.
>
>Variations:
>- Games in which players do not know when the game will end
>- Games in which players know when the game will end.

When this game is repeated some known, finite number of times  and there is only one Nash equilibrium, then collusion cannot work.  
The only equilibrium is the single-shot, simultaneous-move Nash equilibrium; in the game above, both firms charge low price.

## Multistage games

>**Extensive form game**: A representation of a game that summarizes the players, the information available to them at each stage, the strategies available to them, the sequence of moves, and the payoffs resulting from alternative strategies.

![[Skærmbillede 2023-12-16 kl. 22.16.07.png]]

**Nash equilibrium**: 
Player A: Down,
Player B: Down, if player A chooses Up, Down if player A chooses Down.

>**Subgame Perfect equilibrium**: A condition describing a set of strategies that constitutes a Nash equilibrium and allows no player to improve his own payoff at any stage of the game by changing strategies.



