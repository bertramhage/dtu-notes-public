## Consumer behavior
##### Risk aversion
- A **risk-averse** consumer prefers a sure amount of $\$M$ to a risky prospect with an expected value of $\$M$.
- A **risk-loving** consumer prefers a risky prospect with an expected value of $\$M$ to a sure amount of $\$M$.
- A **risk-neutral** consumer is indifferent between a risky prospect with an expected value of $\$M$ and a sure amount of $\$M$.

##### Consumer search
Suppose that three-quarters of stores in a market charge $100 and one-quarter charge $40.

One quarter of the time the consumer will save $100-$40 = $60.
Three quarters of the time the consumer will save nothing
The **expected benefit** from an additional search is 

$$EB = \frac{1}{4}(\$100-\$40)+\frac{3}{4}(\$100-\$100)=\$15.$$
A consumer should search for a lower price as long as the expected benefits for an additional search are greater than the cost of an additional search.

![[Skærmbillede 2023-12-17 kl. 11.27.49.png]]
Consumer should accept prices below the reservation price $R$ and reject prices above $R$.

## Firms behavior regarding risk
##### Manager's risk profiles
- A **risk averse** manager is someone who prefers a risky project with a lower expected value if the risk is lower than a project with a higher expected value.
- A **risk loving** manager is someone who prefers a risky project with higher expected value and higher risk to one with lower expected value and lower risk.
- A **risk neutral** manager is someone who is interested in maximizing expected profits; the variance of profits does not impact a risk-neutral manager's decisions.

>[!example]+ Risk aversion problem
>A manager is considering two projects: to expanding the market for bologna or expanding the market for caviar.
>There is a 10% chance of a recession and a 90% change of an economic boom. 
>![[Skærmbillede 2023-12-17 kl. 11.38.21.png]]
>Q: which project should managers undertake?
>A: T-Bill is out of the question since E(Joint)>E(T-Bill).
>The expected returns of the bologna project is negative so should not be chosen.
>Therefore they should adopt either the caviar project or the joint project. Which project will depend on his or her risk preferences.

> **Producer search**: When producers are uncertain about the prices of inputs, an optimizing firm will use optimal search strategies. These strategies mimic consumer search.

##### Profit maximization
If demand (hence, revenue) is uncertain and the manager is risk neutral, then the manager will want to maximize expected profits by producing the output where the expected marginal revenue equals marginal cost:
$$
E[MR]=MC.
$$
>[!example]+ Profit maximization problem
>How much juice should Appleway Indst. produce given that the market price will be \$2 pr gallon with 30% chance, and \$1 pr gallon with 70% chance.
>Cost function is given:
>$C=200+0.0005Q^2$.
>A: Profits are:
>$\pi =pQ-200-0.0005Q^2$.
>To maximize expected profits the manager equates expected price with marginal cost:
>$E[p]=MC$.
>The expected price is: $E[p]=0.3\cdot\$2+0.7\cdot\$1=\$1.30$.
>Therefore the manager should produce output where 
>$\$1.30 = 0.001Q\implies Q=1,300$ gallons.
>Expected profits are \$645.

## Market regarding uncertainty'

>**Asymmetric information**: When some people have better information than others in a market, the information people have is called asymmetric information.
>
>- Adverse selection refers to situations where individuals have hidden characteristics and in which a selection process results in a pool of individuals with undesirable characteristics.
>- Moral hazard refers to a situation where one party to a contract takes a hidden action that benefits his or her at the expense of another party.

## Auctions

Four basic types of auctions:
- English (ascending-bid)
	- Bidders observe the bids of others and decide whether or not to increase.
	- The auction ends when a single bidder remains.
- First-price, sealed-bid
	- Bidders simultaneously submit bids.
	- The auctioneer awards the item to the highest bidder who pays the *amount bid*.
	- Bidders obtain no information about one another's bids.
- Second-price, sealed-bid
	- Bidders simultaneously submit bids.
	- The auctioneer awards the item to the highest bidder who pays the amount bid by the *second-highest* bidder.
	- Bidders obtain no information about one another's bids.
- Dutch (descending-bid)
	- The auctioneer begins with a high asking price and gradually reduces the asking price until one bidder announces a willingness to pay the price.
	- Bidders obtain no information about one another's bids.

##### Information structures
Bidders have different information structures about the value of their own bids:
- Perfect information
- Independent private values
- Affiliated (or correlated) value estimates

>[!info] Strategies for independent private value auctions
>With independant private values, bidders know his or her own values prior to the auction start.
>
>**English auction**
>Remain active until the price exceeds his or her own valuation of the item.
>
>**Second price, sealed-bid auction**
>Bid his or her own valuation of the item. This is a dominant strategy.
>
>**First-price, sealed-bid auction (strategically equivalent to the Dutch auction)**
>Bid less than his or her valuation of the item. Given $n$ bidders all perceiving valuations to be uniformly distributed between a lowest $L$ and highest $H$ possible valuation the optimal bid $b$ for a player whose own valuation $v$ is 
>$$
>b = v-\frac{v-L}{n}.
>$$

>[!example]+ Strategies of independent private value auctions
>Consider an auction where bidders have independent private values. Each bidder perceives that valuations are evenly distributed between \$1 and \$10. Sam knows his own valuation is \$2.
>Q: Determine Sam's optimal bidding strategy for various auction types.
>
>A: 
>**First price, sealed-bid auction with two bidders**
>Sam's optimal bid is $b=2-\frac{2-1}{2}=\$1.50$.
>
>**Dutch auction with three bidders**
>Sam's optimal bid is $2-\frac{2-1}{3}=\$1.67$.
>
>**Second-price, sealed-bid auction with 20 bidders**
>Sam's optimal bid is to bid his true valuation which is \$2.

>[!info] Strategies for correlated values auctions
>Bidders do not know their own valuations for an item, nor others' valuations.
>
>*Winners curse: The bidders estimate of the item's value exceeds the estimates of all other bidders.*
>
>To avoid winner's curse in a common-value auction, a bidder should revise downward his or her private estimate of the value.
>
>The winner's curse is most pronounced in sealed-bid auctions since bidders don't learn about other player's valuations. English auctions in contrast provides bidders with information, therefore, bidders may have to revise up their initial bids.

##### Expected revenues in auction types
| Information structure | Expected revenues|
| ---------------------|-------------------|
|Independent private values| English = Second-price = First-price=Dutch|
|Affiliated value estimates| English >Second-price>First-price=Dutch|








