Imagine
=======

Imagine a future where abundance, not scarcity is a norm. In this world we tradle the energy we pour into work, for coins we use to pay for living expenses and our whims.

Who
===
Tradle is a community that shares a belief that freedom and commerce are necessary ingredients for happiness. 

How
===
At Tradle we want to enable the blockchain to provide consensus for any database transactions. We came up with several designs (and so far prototyped one of them), but each has its issues. For the underlying DHT and files we used TomP2P, explored OpenKad and have now rewritten with bittorrent-dht which is battle-tested as part of the Popcorn Time app.

We am aware of Permacoin, Filecoin, Maidsafe, Tahoe-LAFS - good ideas there - but none of them quite fits the bill. We want a design that is specific to storing transactions in the DHT/DFS, not large media files, one that derives security properties from the blockchain to help deflect attacks on the DHT, does not introduce a new blockchain and has high encryption guarantees - not only the transaction body is encrypted, but also the location, with the shared secret of transaction participants. We also need dynamic access rights allocation, so if I sent you an order, you could later share it with your accountant.

We discussed the subject of "DHT + blockchain" with bitcoin core devs Matt, Jorge, Pieter and Mike. They all agree this is not simple to achieve and they expressed a concern "do not bring DHT security problems into the blockchain", and "do not bloat the blockchain".

So our goal is to have blockchain help us secure the DHT, without any adverse effects on the blockchain and with the minimum bloat (using 40 bytes in OP_RETURN).

