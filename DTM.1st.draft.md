1st Draft 
# Direct To Market(DTM)

## A Distributed Trustless Marketplace 

## Decentralized Autonomous Organization (DAO)

## Abstract:

1.	Content provider, (BIP 44 address), and consumer identity, (BIP 44 address), hosted on the RVN BC through the use of Unique tokens.  

2.	Content providers host files on encrypted Inter Planetary File System, (IPFS), network and set price.  

3.	Keys for individual files delivered to the consumer through metadata written into purchase transaction transmitted and recoded via RVN BC.

Using the methodology detailed in RIP 11, https://github.com/MangoFarmAssets/rips/blob/master/rip-0011.mediawiki, Appendix 1, a unique token, 
with a public PGP key, is created for any address that needs access to the encrypted IPFS network.

A.	Consumer access, read only, to the network would only require a verified payment method.  

B.	Content provider access, read/write, to the network would require a BIP 44 address and full KYC.  KYC information would be required to help 
enforce copyright laws and for accounting. 

Content providers would encrypt files using a set of proffered encryption algorithms, upload files and keys to the encrypted IPFS network and set 
the price.  EBooks, videos/movies, newsletters, research data, music, ect… Encryption keys, tags, descriptions, thumbnails, icons, pictures or 
whatever material need for marketing and sale are uploaded with content through a simplistic web API.  (At this time, depending on cost and 
other factors, the IPFS hash may be pinned to a unique RVN token and sent to the content provider.  This would not only show owner ship but 
also provide indexing data on the RVN BC.) Information on content for sale can be delivered to any 3rd party website or phone app through a 
set of APIs that query the network and BC.  Consumers could browsee and purchase content on any number of platforms.  When a purchase is made, 
a token, containing metadata, with the encryption keys for the files purchased, is sent to the purchasing address. Any 3rd party software could 
display the content of the file once it is un-encrypted.

## Function:

1.	IPFS Hosting Network: (IPFS encrypted container?)  Network could/would be supported 
by each content provider. This program will be discussed in more detail later under the marketing section.  
Access would be limited to known, tagged addresses.  This would allow the function of read/write limitations and also limit file exposure encase 
single file encryption keys were stolen. General management of the network could be almost entirely automated, preferably done with a dapp, 
“Gatekeeper”, run on the same IPFS network that it is managing.  

The Gatekeeper would perform several functions:

a.	Create read access keys
1.	Receive relevant data, user, pass, 2fa, payment information from client app
2.	Receive client generated RVN BIP 44 wallet address as outlined in RIP 11, Appendix 1
3.	Receive client generated, with user input, OpenPGP key pair
4.	Create JSON file w/public key and upload to public IPFS network. (which IPFS network?)
5.	Create unique token and tag address w/token as outlined in RIP 11, Appendix 1

b.	Content hosting
1.	Check unique asset tags against the RVN BC for network authorization
2.	Collect needed information from form data
3.	Post file w/copyright data to IPFS and BC ledger
4.	Create unique token, per content bundle, sent to content provider address (Price)
5.	File could be black listed by sending Unique token to non verified address
6.	Would stop further sales but allow access for purchases already made

c.	Gatekeeper 
1.	Check unique asset tags against the RVN BC for network authorization
2.	Return data from authorized 3rd party queries
3.	Indexing

d.	Granting individual file access
1.	Receive purchase notification from authorized 3rd party. (transaction on RVN BC? See purchase function)
2.	Create JSON file w/file encryption key and encrypted with consumer public key. Upload to encrypted IPFS network.
3.	Using RVN messing function, send non unique token to address with IPFS hash. (note, JSON file may need to be amended for each purchase. Methodology TBD)

e.	Read/Write access granted via human interaction
1.	Full KYC information collected and stored (BC?)
2.	Audit trail for all copyright legal matters

f.	Receive “receipts” messages from client to initiate file access

g.	Black/White list function

h.	Copyright database search function

((Could Gatekeeper be an encryption wrapper running on the existing public IPFS?))

2.	“Client”: Client side utility that interacts with IPFS Network dapp and with 3rd party GUIs to facilitate the functions of the marketplace

a.	 Create BIP 44 address and OpenPGP key pairs

b.	 Collect data, user, pass, 2fa, payment information

c.	Send data to IPFS Gatekeeper to issue unique token as key to client utility

d.	Receive and hold token(s) for function of marketplace

e.	Scan BC for “receipts”, IPFS files associated with address

f.	Facilitate sending purchase data to Gatekeeper 

g.	Index purchases for address for display in 3rd party app or website

h.	Process keys from IPFS/JSON file, un-encrypt purchased files and send data to 3rd party app for display

i.	Scan and index IPFS network and send data about content for sale to 3rd party app for display

j.	Write “receipt” JSON file and send to IPFS

k.	Broadcasts a “receipt” message by sending unique ID token to own address.  This give chain of “receipts” on the BC.

Restricting Network/File Access

There are several reasons the administrator may want to restrict access, to either the network or particular files, of certain addresses. 
The RVN BC has the functionality through the use of the “Tag” and “Restricted Asset” functions to address these needs.  More research is needed 
to determine the exact methodology used to facilitate these functions.  There are also may be a need to “Blacklist” a file from the entire 
community.  The best mythology has yet to be determined but the use of unique assets could be one solution.

## Payments

Consumer would be able to make purchases using fiat or crypto currency.  Funds used in purchase would be converted to RVN (Changely?) and sent to 
appropriate parties for instant payments when available.  60% would go to the CP address, 30% would go to the company/host of the system and 10% 
would go to the “Agent” who services the content providers they sign up.  CP and Agents may break up their commission to multiple wallets.  This 
would allow an outside back office company and/or an agency to dole out payments instantly and have accounting records recorded to the BC. The RVN 
Reward function will be employed.  For each CP 1000 “CP Payment” tokens will be created. 300 tokens will go to the host designated address, 100 to 
the Agent address and 600 to the CP address.  When a purchase is made the Client will pay out the total amount of RVN collected for each content 
unit sold, in equal amounts, to each CP Payment token corresponding to the CP of the content sold.  This allows CPs and Agent to divide up their 
payment such as in the case of an Agent using a Backoffice company.  This also allows for instant settlements for all parties. 

A 3rd party like Changely could be used to convert to RVN and for the Content creator and Agent to convert back to fiat or other coin.  Also the use 
of crypto to VISA/MC might be employed by CPs and Agents

## Payment Flow

Consumers would browse content and select items for purchase.  Items would be added to cart and all payment information is collected at time of checkout.  
This can be done by any 3rd party app or web site that is able to scan the network and access the APIs of the Client.  The host would create a web site 
and apps for using the market place but would also promote the marketing of the content by 3rd party sellers.  

## Upon checkout:
1.	All necessary information and RVN for purchase is sent to Client via APIs from GUI 
2.	Client generates JSON file “receipt”, and posts file to IPFS
3.	Client broadcasts the receipt using the RVN message function by sending the unique users token back to the sending address
4.	Gatekeeper reads receipt from Client
5.	Gatekeeper generates encrypted JSON file with access keys to files purchased using the RIP11 ~ 13 protocols and post to IPFS
6.	Gatekeeper sends non unique token to Client containing the IPFS hash using the RVN message function
7.	The chain of receipts and encrypted JSON key files are kept on the RVN BC/IPFS
8.	Any 3rd party application could query the Client and/or the BC to obtain the consumers’ “library” of purchases for display

((Will transaction be fast enough?  Will Lighting network need to be employed? Another way to “Bond” purchase transactions for instant delivery of content?))

## Content providers:

A web site for content provider to upload files and all pertinent information about content for sale would be needed.  Write access would be granted 
via human interaction from the host after all KYC information was collected.  Using the message function of RVN an IPFS file could be written to the RVN BC 
for indexing.  Possible unique token issued for each file/package uploaded to encrypted IPFS.  This would allow a CP to transfer ownership of content for 
sale, such as song or book rights.

1.	Marketing system and cost for agents to use 
2.	Cost to sign up to provide content
3.	RPi4 with RavenlandOS to support the network, scaling and persistency  
4.	Marketing data, icons, file names, thumb nails, samples, cover pictures….. hosted on public IPFS
5.	Encrypted content for sale hosted on encrypted private IPFS

## Marketing:

Music: Give the content provider a way to generate a list of codes that would allow a user to get a free RVN unique consumer token to access the network.  
The current price of 5 RVN for a unique token is a barrier to adoption and will be address in a later RIP.  With this list musicians could generate flyers 
to give out at their events so that fans and join the marketplace and purchase content.  CPs could also generate discount codes for reduced or free songs.  
Artist would still have to pay host fee.  RVN redemption codes?  Samples hosted on the public IPFS.

## Development:

## Agent/Agency:

Key to the adoption of the marketplace by CPs will be the “Agent”.  The Agent can be any business entity that registers to sell the services provided by the DTM.  
The Agent would be responsible for marketing, signing up and providing customer service to CPs.  Agents would receive 10% of the gross revenue for each sale a 
CP made, as commission. Agents would be separate companies and subject to free market forces and the laws of the country they are lawfully bound by.

## Backoffice Services:

A separate company, to provide technical services to Agents, for a % of the Agent’s commission.  This company would handle the hands on technical aspects of 
registering and posting services for the CP from the information collected by Agents.  Agents would not have to use this service but it is a common factor 
in other commission based sales industries and would greatly increase the speed at which new Agents could be on boarded and producing.

## Content Provider (CP) sign up:

Agents will market to CP.  In order to sign up a new CP, KYC information must be collected and entered into a database.  This is very important for copyright 
enforcement and Agent will bear some responsibility in the validation of this information.  This can be done via a web site but must await human approval 
from the host organization.  Once approved, the Agent will then create a custom address, A customized RPi4 w/RavenlandOS, a Unique ID token and Payment tokens 
for the new CP.  This could be created using a Virtual Machine and the flashed to a SD card for any RPi4 to use.  This custom OS RPi4, either virtual or 
real, would then be used as the gateway for the CP to post content for sale.  This would also allow the Agent or another 3rd party of the CP’s choosing to 
administer the posting of content.

RPi4 
Ravenland has developed a linux based OS image file for the Raspberry PI4, (RPi4). This OS contains fully functional wallet, a running IPFS host and many 
other build in functions for supporting the RVN and IPFS network.  This OS is open source and anyone may download and use it.  For the purpose of the DTM 
a one size fits all would be available for anyone to download and support the network.  For CPs the OS could be customized to contain their unique asset 
ID/Key and to be the gateway to the IPFS to keep their published content persistent.  There are a multiple of other functions this setup could provide to 
both the CP and the network.  This package could be included in the signup cost to the CP.  This would all be facilitated by the Agent/Backoffice.  T


Naming Convention for Tokens

CP Tokens. Limited to 30 characters.  Root Host Token Name = 5. Type = 2. CRC32 Hash of address(RIP11) = 8.  Reserve 8 spaces for other functionality. 
5 spaces for Content name used for catalogue and ownership. 

Example unique CP Token: DTMWW#CP_nIU87rRi
Example CP uploaded unique Content Token: DTMWW\CP_nIU87rRi#K09Jy
Example CP Payment Tokens: DTMWW\CP_nlU87rRi = 1000.  

Agent Tokens. GA Tokens. Limited to 30 characters.  Root Host Token Name = 5. Type = 2. CRC32 Hash of address(RIP11) = 8.  Reserve 13 spaces for other functionality.

Example unique Agent Token: DTMWW#GA_RvKj7r5i

Consumer Tokens. CT Tokens. Limited to 30 characters.  Root Host Token Name = 5. Type = 2. CRC32 Hash of address(RIP11) = 8.  Possible linking of 2nd 
address CRC32 = 8. Reserve 5 spaces for other functionality.

Example unique CT Token: DTMWW#CT_RnC8upE3

Encrypting Asset Metadata (CP)

A CP who wishes to post encrypted asset metadata, content for sale, can do so in the following manner:
A.	Access content posting web portal using RPi4 gateway
B.	Add content for sales along with any relevant information about content for marketing and indexing to the web portal
C.	Review and submit, at which time the Gatekeeper will perform the following actions:
1.	Encrypt the desired files referenced in the metadata JSON (e.g., one or more of the ipfs_attachments) using a cryptographically secure symmetric key 
algorithm. The algorithm chosen is a matter of user preference. The reference implementation for this RIP uses TripleSec, which double-encrypts the data with 
Salsa 20 and AES.
2.	Create a metadata JSON file referencing file location and encryption key.
3.	Create a unite ownership token with copyright and other needed information.  Could be used for a number of different functions including a Black/White list.
4.	Create 1000 sub tokens for dividend payouts.  This payout option cost 100 RVN per issuance and might only be used in specific circumstances.  Most content 
purchases would pay out along the CP’s 1000 sub tokens, created at the time the CP was added to the network.
5.	Index any relevant data 
D.	When consumers purchase content their Client will perform the following actions:
 
1.	Create a JSON file with purchase information and public PGP key
2.	Upload JSON file to IPFS to get location hash
3.	Send consumers unique token to sending address with IPFS hash to “broadcast” the message, “receipt”, on the DTM channel. 

E.	 When the Gatekeeper receives a broadcast receipt it will perform the following actions:
1.	Create a metadata JSON file.
2.	Encrypt the desired files referenced in the metadata JSON (e.g., one or more of the ipfs_attachments) using a cryptographically secure symmetric key algorithm. 
The algorithm chosen is a matter of user preference. The reference implementation for this RIP uses TripleSec, which double-encrypts the data with Salsa 20 and AES.
3.	PGP encrypt the shared symmetric key used in step 2 above, using the PGP public key of each intended recipient. This public key can be obtained from the Address 
Encryption Tag associated with each recipient's encryption address.
4.	Add the encryption information for each recipient to the metadata JSON.
5.	Send a non unique token to the intended recipients with the IPFS hash of the JSON file using the messaging function of the RVN BC.
This method, which PGP encrypts only the symmetric encryption key, reduces file bloat and eliminates the need to PGP encrypt the entire file multiple times with 
the PGP public key of each additional recipient.

This RIP can be used with any method to generate the JSON file, as long as the relevant encryption information is included within it. For example, RIP14 contains a 
specification for generating the metadata JSON that includes encryption data. Alternatively, if the metadata JSON file is created using the Ravencoin Metadata 
Specification, encryption information for each recipient can be added as a nested object at the end of the metadata JSON to encrypt the contents of contract_url:
{ ...
	"encryption": {
		"algorithm": "<e.g., AES, TripleSec>",
		"recipients": {
			"<recipient 1 encryption address>": "<PGP encrypted symmetric key to recipient 1>",
			"<recipient 2 encryption address>": "<PGP encrypted symmetric key to recipient 2>",
			"<recipient n encryption address>": "<PGP encrypted symmetric key to recipient n>"
		}
  	}
}

This method can also be used with other metadata structures, such as the one being worked on here by adding appropriate version and schema information.

Partnerships
It might be beneficial to all to work with other entities such as the Project Gutenberg, Sacred Texts and Wikipedia.  This could give added exposure to all, 
greater access to content and added funding sources.  There could be many pros for a partnership of this kind and should be explored.

Future Expansions

Subscription TV service.  Either selling single shows or through monthly updates to encryption files companies could provide constantly updated content to consumers 
who pay a subscription fee.

Selling of Real World Items, Cash On Delivery.  A consumer purchases a Certificate of Authenticity, COA for an item.  Seller ships the item with a QRC for payment.  
Shipper has consumer scan code thus signing for package and releasing payment.  I walked in to a shop on 12/6/19 and the merchant was receiving a COD package for 
merchandize to sell in his shop.  Both the FedEx shipper and the merchant were complaining how difficult the COD process was.
