Imagine
=======
Imagine a future where abundance, not scarcity is a norm. In this world we tradle the energy we pour into our work, for coins to pay for living and our whims.

Who
===
Tradle is a community that shares a belief that freedom and commerce are necessary ingredients for happiness and that we can solve this problem with the new technology reducing the governance need to a minimum.

How
===
We want to build a decentralized commerce network, which we call Tradenet, and for that we need some basic building blocks. First step if to enable the blockchain to provide consensus for any database transactions. Centralized SaaS model of the Web apps, from Google Docs to Salesforce, provides a lot of benefits for collaboration by sharing data and business processes. But SaaS model is flawed as all the data are up for grabs by hackers and the governments. Unfortunately we spend years discussing and legislating 'do not track' cookies policies by companies, but tolerate complete surveilance of all our communications.

It is time to create an architecture that does not lend itself to so much concentration of data in one set of hands. Our hope is that this architecture should allow small teams and individuals outperform large corporations.

Specifically we are designing a metaprotocol on top of a blockchain that allows transaction to carry aditional data outside of a blockchain, yet preserve the same concensus guarantees and provide even more guarantees for data privacy. Existing metaprotocols like Mastercoin (rebranded as Omni) and Counterparty are storing all data on the blockchain which causes a lot of grief to core bitcoin developers and mining pool operators.

We need a new metaprotocol that is storing the data on another p2p network with high reliability. We came up with several designs (and so far prototyped one of them), but each has its issues. For the underlying DHT and files we used TomP2P, explored OpenKad and have now rewritten with bittorrent-dht which is battle-tested as part of the Popcorn Time app.

We do not want to turn a blockchain into a database, but rather we want it to serve as a global transaction log, with which we wil synchronize our databases. We am aware of different decentralized storage mechanisms, like Permacoin, Filecoin, Maidsafe, Tahoe-LAFS - good ideas there - but none of them quite fits the bill. We want a design that is specific to storing transactions, not large media files, one that derives its security properties from the blockchain, does not introduce a new blockchain and has high encryption guarantees - not only the transaction body is encrypted, but also the location, with the shared secret of transaction participants. We also need dynamic access rights allocation, so if I sent you an order, you could later share it with your accountant.

We discussed the subject of "DHT + blockchain" with bitcoin core devs Matt, Jorge, Pieter and Mike. They all agree this is not simple to achieve and they expressed a concern "do not bring DHT security problems into the blockchain", and "do not bloat the blockchain".

So our goal is to have blockchain help us secure the DHT, without any adverse effects on the blockchain and with the minimum bloat (using 40 bytes in OP_RETURN).

Migration
=========
We are in the process of migrating github repositories and wiki [from another github location](github.com/urbien/tradle/wiki/A-starting-point).

Our [new wiki](https://github.com/tradle/about/wiki) is still under construction, but give it a shot.
