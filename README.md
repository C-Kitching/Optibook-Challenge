# Optibook-Challenge

Algorithmic trading challenge carried out during Optiver's 2023 Spring Insight days.

The challenge was to build an automated strategy for dual-listing of a fictional stock "Phillips A" and "Philips B" which was traded on two, differently liquid, exchanges againsts various bots and other market particients. 

## Algorithm

Our algorithm is a delta-neutral market-making algorithm that traded on the illiquid market and then instantly hedged on the more liquid market.

Our trader would always hold a bid and an ask in the illiquid market, making sure that the bid-ask spread for B is wider than that of A inorder to ensure we can always instantly hedge the position on the liquid market while making a profit. Thus, this is a low risk strategy as the position is always close to zero.

We can decrease the risk more by having a buffer to ensure a minimum profit for each trade, which avoids common low-profit trades otherwise. 

We added "unwinding" to ensure that the positions held actually approach zero and we wouldn't end up in a situation where we are long 200 and short 200 for example. 

Overall, this algorithm provides good PnL with low risk. 
