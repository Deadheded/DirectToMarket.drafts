1st draft

# DTM Nuts and Bolts

The Marketplace runs on existing technology and utilizes systems and procedures from open sources. In
order to understand how the Marketplace functions you need to understand a little bit about the
technology behind it.

The first piece is the Inter Planetary File System or IPFS. IPFS is a distributed system for storing and
accessing files, websites, applications and data. Please follow the links to learn more about IPFS and
why it is vital to the function and ideology of the Marketplace.
https://docs.ipfs.io/introduction/overview/ https://docs.ipfs.io/

In addition to the open IPFS network, the Marketplace will also employ an encrypted IPFS network
developed by https://www.ravenland.org. Ravenland currently provides a number of IPFS and RVN
services including https://mypin.io/#/. They also have developed RavenlandOS for the RPi4, which will
be employed for each content provider.

Second is the Ravencoin Block Chain, RVN. This specific BC combined with IPFS has all the underlying
function and features needed to make the Marketplace work. The most concise article about the
functions of RVN was written by its lead developer Tron Black:
https://medium.com/@tronblack/ravencoin-a-securities-token-roadmap-47ae1d9dac26? Although the
article is about using RVN for securities, most of the features will be used to facilitate the function of the
Marketplace.

One of the more vital uses of RVN was developed by Mangofarms. Specifically “Asset Metadata
Encyption Protocol”, otherwise known as RIP 11.
https://github.com/MangoFarmAssets/rips/blob/master/rip-0011.mediawiki. You can use this function
now to send private data to anyone. https://medium.com/@mangofarm/mango-farms-new-release-ishere-
59f1830eff82.

A quick explanation, from the RVN lead developer, of the IPFS and RVN connection.

Derek Edward Schloss: How does the information I upload to IPFS integrate with my Ravencoin assets?

Tron Black: A few ways. With IPFS, the hash of the file is used as the file name. So if you upload a movie
file into IPFS called “Bestmovieever.mpeg” on four different occasions, the same 34-character hash⁸ would
be given each time to that file, and that specific .mpeg would only be stored one time. In other words,
there would only be one master copy. Anyone can access that file via the 34-character hash, and there’s
no way to tamper with that data in IPFS without it becoming a different hash. This means if you stick that
34-character hash into an asset on Ravencoin, then you create an immutable asset, that can be traded
freely, with a link to immutable data.

Derek Edward Schloss: Just so I’m clear, it’s possible to upload things like books or music or movies into
IPFS, and then link this digital information to token assets created on the Ravencoin platform? I guess I
could see Ravencoin moving all types of digital information in token form, jumping from wallet to wallet.
https://medium.com/securitytokenacademy/ravencoin-tron-black-131db123f025

All of this will show how encrypted content can be hosted on the IPFS and delivered to a specific RVN
address and only that address can decrypted the content.

So how does all this work to create a Marketplace?

There are several pieces that make all this work; Content Providers (CP), Consumers, Server side
application (Gatekeeper), Consumer side application (Client) and the GUI’s. The GUIs could be any 3rd
party software that wishes to interact with the Client and Gatekeeper app to market any content for
sale.

1. IPFS Hosting Network: The entire network is encrypted based on systems developed by
Ranveland.org. These limits file exposures encase encryption keys are compromised.
Read/Write access is limited to known, KYC, tagged addresses. General management of the
network is almost entirely automated through the use of a distributed application, Gatekeeper.
This dApp resides on the same IPFS network that it is managing. The Gatekeeper would perform
several functions:

a. Create read access keys
1. Receive relevant data, user, pass, 2fa, payment information from client app
2. Receive client generated RVN BIP 44 wallet address as outlined in RIP 11, Appendix 1
3. Receive client generated, with user input, OpenPGP key pair
4. Create JSON file w/public key and upload to public IPFS network. (which IPFS network?)
5. Create unique token and tag address w/token as outlined in RIP 11, Appendix 1

b. Content posting
1. Check unique asset tags against the RVN BC for network authorization
2. Collect needed information from web form data
3. Post file w/copyright data to IPFS and BC ledger
4. Create unique token, per content bundle, sent to content provider address (Price?)
5. Create post JSON file with encryption key and location of content
6. Index data

c. Gatekeeper
1. Check unique asset tags against the RVN BC for network authorization
2. Return data from authorized 3rd party queries
3. Indexing

d. Granting individual file access
1. Receive purchase notification from authorized 3rd party through Client. Create JSON file
w/file encryption key and encrypted with consumer public key. Upload to encrypted
IPFS network.

e. Using RVN messing function, send non unique token to address with IPFS hash.

f. Black/White list function

g. Copyright database search function

2. “Client”: Client side utility that interacts with RVN BC, the Gatekeeper dApp and with 3rd party
GUIs to facilitate the functions of the marketplace

a. Create BIP 44 address and Open PGP key pairs
b. Create 12 word wallet recovery phrase
c. Wallet for tokens and payment in RVN (could interact with any compliant wallet?)
d. Send data to IPFS Gatekeeper to issue unique token as key to client utility
e. Scan RVN BC past purchases, JSON “receipt” files associated with address
f. Interacts with 3rd party GUI to facilitate purchases
g. Write JSON file, receipt and posts to IPFS
h. Broadcasts a “receipt” message by sending unique ID token to own address. This records a
chain of “receipts” on the RVN BC and alerts the Gatekeeper about purchase.
i. Index purchases for address for display in 3rd party app or website
j. Process keys from IPFS/JSON file, un-encrypt purchased files and send data to 3rd party app
for display
k. Scan IPFS network and RVN BC and index data about content for sale to 3rd party app for
display

Payment Flow

Rights Management, featuring a royalty distribution platform for multiple stakeholders in the media
value chain

Consumers would browse content and select items for purchase. Items would be added to cart and all
payment information is collected at time of checkout. This can be done by any 3rd party app or web site
that is able to scan the network and access the APIs of the Client. The host would create a web site and
apps for using the market place but would also promote the marketing of the content by 3rd party
sellers. 

Upon checkout:
1. All necessary information and RVN for purchase is sent to Client via APIs from GUI
2. Client generates JSON file “receipt”, and posts file to IPFS
3. Client broadcasts the receipt using the RVN message function by sending the unique users token
back to the sending address
4. Client sends payment to holder of payment tokens
5. Gatekeeper reads receipt from Client
6. Gatekeeper generates encrypted JSON file with access keys to files purchased using the RIP11 ~
13 protocols and post to IPFS
7. Gatekeeper sends non unique token to Client containing the IPFS hash using the RVN message
function
8. The chain of receipts and encrypted JSON key files are kept on the RVN BC/IPFS
9. Any 3rd party application could query the Client and/or the BC to obtain the consumers’ “library”
of purchases for display
10. Encrypted data is accessed by the Client and delivered un-encrypted to the GUI
Will transaction be fast enough? Will Lighting network need to be employed? Another way to “Bond”
purchase transactions for instant delivery of content?
Content providers

A web site for content provider to upload files and all pertinent information about content for sale
would be needed. Write access would be granted via human interaction from the host after all KYC
information was collected. Using the message function of RVN an IPFS file could be written to the RVN
BC for indexing. Possible unique token issued for each file/package uploaded to encrypted IPFS. This
would allow a CP to transfer ownership of content for sale, such as song or book rights.

1. Marketing system and cost for agents to use
2. Cost to sign up to provide content
3. RPi4 with RavenlandOS to support the network, scaling and persistency
4. Marketing data, icons, file names, thumb nails, samples, cover pictures….. hosted on public IPFS
5. Encrypted content for sale hosted on encrypted private IPFS
