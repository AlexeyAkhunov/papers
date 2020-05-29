Today we will talk about gas. Gas in Eth1.0 is required for the users (non-miners) to make changes in the Ethereum State.
Think of State as a conformation of proteins in biology, and changing conformation either requires energy or releases energy.
ETH on users’ account then plays a role of energy store.
In order for ETH to be converted to gas and be used for computation and changing the state,
a transaction needs to be created and included into a block.
Since blocks have block gas limit, it effectively limits the rate of synthesis of gas from ETH (but does not limit the ratio
of ETH/gas conversion).
Another property of gas is that once synthesised, it has to be immediately used, otherwise it burns or
gets converted back to ETH.
So there is no good way of storing excess gas and then releasing it slowly
(this is what happens all the time in biological systems - release of energy happens by gradual chemical conversions,
in a slow and controlled fashion). You can think of the Ethereum transactions as energy explosions that always
have to be initiated by ETH holders and permitted by miners to be included into blocks,
so that ETH can be converted into gas to effect the change in the State. Smart contracts can store ETH,
but they cannot store gas, and they have no way of initiating ETH=>gas conversion and effect state changes.
Therefore, once ETH has landed into a smart contract, for this ETH to be converted into gas,
it first needs to to back to a user, and then converted in an  explosion.

What if we relax this? Lets say it is possible to store store gas rather than using it all up explosively. In order to
store it, we need a way of specifies what would trigger the release of that gas and directing it to some computation that
results in a state change. Without trigger the gas will never be release, so it is useless, and without resulting state change
it is also useless computation. What could trigger the release? The first thing that comes to mind is another state
change, or perhaps an event (log in ethereum terms). The latter seems more elegant, but both need to be thought about.
How will this be executed? Here is one possible mechanism, which requires some clever data structures inside the
blockchain engine, but it is nevertheless cool as a concept. Currently, there are some mandatory state changes that
each block has to do regardless of whether it has any transactions or not. It needs to correctly reward the miner and
the miners of the uncles. There could be other mandatory things added to that, like reactions to events, in the order
of their appearance. Reacting on 
