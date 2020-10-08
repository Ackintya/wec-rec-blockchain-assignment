## wec-rec-blockchain-assignment

This is a game of coin flip betweeen two participants.

There is an oracle/judge who decides the results and is responsible for prize/bet distribution.

The oracle also deposits a caution sum which is redistributed to participants incase the oracle does not respond within time.


The rules and the instructions for the game are mentioned below:


1.First, The challenger/owner deploys the game giving betting/registration time and the minimum oracle fee as input.

2.The acceptor of the challenger first has to place the bet and then choose the oracle by giving it's address in Chooseoracle().

3.The challenger can do them in any order.

4.If the bets or oracle addresses of both inputs are different then the one who put the proposal first has to repropose his proposal/betamount or the latter one can't proceed.

5.There is also an option to view the exisiting proposal for oracle.

6.When placing a bet, user has to put their outcome preference too and both players can bet on same outcome too and in that case all the money goes to the oracle.

7.The General public can see the bets and the betting amount after the betting period.

8.After the betting period, the oracle has to calculate the result by opening result where the winners are rewarded and the oracle is given back his deposit and the fee.

9.If the oracle doesn't respond within time. His deposit will be distributed to the players along with their bets.

10. After the deadline is reached and the money is distributed, the game selfdestructs.


Calculations:

1. The result was calculated using Keccak256 with the block's timestamp and the current betamount as parameters to create a hash that is difficult to calculate.

2. The deadline time is twice the betting time.

chooseoracle(): used for proposing the oracle (not to be used by acceptor before placing bet)

placebet():takes the outcome and is payable

depositfororacle(): For oracle to deposit the money and is payable

showoracleproposal(): Toggle to view the current proposal

result(): used by oracle to calculate outome and reward winners and conclude the game

flipcoin():It calculates the outcome returns it to result() and is private.

autobetback():It is to toggled by challenger/acceptor after the deadline is reached.
