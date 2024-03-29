# Problem
# Ethereum Blockchain implementation for a Road Toll System
The project represents a regulated, system of toll roads. Vehicles pay to drive on them. It is regulated in the sense that there is an entity whose role it is to ensure some rules for participants. The end goal is to have all, part or nothing of such a somewhat decentralised system run on an Ethereum blockchain.

# Participants
This project caters to all of them and they should each hold a piece of the checks and balances:

The regulator
The road operator(s)
The toll booth(s)
The vehicle(s)
The driver(s)
Prices
Prices are defined in Ethers. In other words, road operators will not launch an ICO on their "road use" token ;). You are free to decide how high the prices are, by which criteria and by whom prices are decided.

# Proposed Solution
# Project Architecture
Given the project description, my own understanding would be to design the solution into a 3 layer based architecture with each layer dealing with or attempting to solve a specific problem area rather than having everything run on the blockchain. The project would be devided into the following:

1. **DApp Layer** - Decentralised/P2P, Immutable, distributed ethereum blockchain layer that ensures data integrity with Smart contracts processing specific financial, identity and transaction specific logic. The Blockchain Layer doesn’t need: Storage, Business Rules (complex app specific information, location awareness, KYC information etc), instead of trying to use one public network for all concerns, it is better to use it for what it was specifically designed for and accept the fact that public blockchains are a terrible storage solution and will struggle to scale. It is not an AWS or Google Cloud or a conventional NoSQL or SQL database capable of running a billion-plus transactions per week. The DApp layer will be strongly used for“Pointers” or “hashes” powered by Merkle Patricia Tries and will consistently and constantly create, track, verify and validate transactions within a distributed ledger. This is good design as it ensures that all transaction data is publicly available at all times, it is trackable and verifiable, ownership is kept within a public register and all users can be validated and identified upon interaction with the system or upon request. This models also makes it possible for this DApp to be build as a blue print for a global scalable system as well, because it is not "hardcoded" to a specific financial system or model it can be applied to any other similar application as all that is required is to key in the subsequent layers i.e specific business rules, specific UIs and specific storage technology and leverage the strength and utility of open, distributed and incentivized blockchains for a part solution and complete the solution “off-chain” using different types of technologies that have been built and have matured over time to those specific use cases.
2. **Business Rules Layer** - Comprised of distributed service driven architecture, this layer would be driven by a distributed set of servers that provide the business logic and APIs that connect different aspects of the system. This would include APIs that link with tracking systems, GPS, Social media services, live feeds, computer vison and AI and expose data within the system to 3rd party applications. This layer interacts with the Data storage layer as well as the DApp layer. If we need to improve the application this is what we touch and interact with, if we need to change or add more functions, IOT devices, new technology this is the layer weplay around with. We avoid enforcing this layer into the DApp layer because the DApp layer unlike other layers is immutable. Once a contact is deployed its there for good and connot be modified (only in case inpoint of upgradable contracts) but this brings in the ability for tempering and un-anticipated results, I would like to keep the DApp layer as secure, as testable and as compact as possible.
3. **Data Storage Layer** - Comprised of SQL / NoSQL databases that store static data, not all data relevant to the system should be stored on the blockchain as this would increase the overal cost of interacting with the Ethereum Network so static data is kept off-chain that is frequent or semi-frequently accessed for reporting and presentation.  This layer doesn’t need: Open-Access or limited transaction payloads due to block sizes or other public blockchain constraints, this layer is also low cost as each read or write does not involve any gas cost and this type of service is easy to set up and is used on a pay per use basis, you only pay for the data you need to keep. This results in very limited raw data is bing recorded and kept on the public blockchain; the majority of data is recorded in the Data Storage Layer that we scale out and distribute over clustered servers such that it behaves like a distributed relational or NoSQL database (depending on the use case). The data-store is then configured to auto-hash, in bulk, transactions sets onto a public chain, at any required interval, creating a merkle-tie-“receipt,” which notarizes and validates the full dataset hosted on the private data-store. This compartmentalization of data ensures the absolute security and privacy of participants’ full transactional data.
4. **Front End Layer** - Comprised of Web clients, thin clients and light clients that users use to interact with the Ethereum blockchain and the application business rules. This layer directs relevant users to relevant information, seperates concerns and ensures a uniform user experience across all platforms. THis layer wraps the Business Rules two layers into a useful business application. The Application Layer is the “connector” into and out of the Data Storage Layer, through the Business Rules layer (and from there, into the public blockchain, for the underwriting of data integrity).

# Ethical Considerations
- Environment effects

Firstly, the environment. This is because raw computing power is what drives the technology. Blockchain networks rely on encryption and the solving of complex mathematical puzzles, the amount of computing power needed to run them is enormous. According to internet sources: Morgan Stanley, the Bitcoin blockchain alone will use as much power in 2018 as the entire nation of Argentina. Bitcoin’s current estimated annual electricity consumption is 61.4 TWh. That’s 1.5 percent of the United States’ annual consumption. UK-based energy comparison service PowerCompare says the total annual electricity usage of the Bitcoin blockchain exceeds that of 159 nations. Bitcoin is now responsible for 0.6 percent of the world’s entire electricity usage. This will only seem to increase as there are more complex applications and systems that solely depend on the blockchain and run on it full time. The system would therefore be contributing positvcely towards higher global power consumption and ultimately global warming.
- Blockchain Privacy Issues

If a blockchain is public, every transaction ever recorded on the blockchain is available for anyone to look at.
Of course, that doesn’t necessarily mean that someone will be able to identify you. However, the very fact that so much information is available in the public domain runs against longstanding norms, especially in the financial, legal, and healthcare sectors, all of which typically have robust privacy requirements.
- Blockchain Legal Issues

1. **Jurisdiction:** In a decentralized environment where nodes exist around the planet, how do we establish the correct set of rules and laws to apply? Different countries have very different approaches to titles, ownership, contracts, and liabilities.
2. **Decentralized Autonomous Organizations (DAOs):** Consider a typical legal system where both individuals and organizations participate. In many cases, they even have similar rights. How does that apply to DAOs? They run on smart contracts and require almost zero input from users—they are just lines of code—and yet they can perform tasks like traditional companies. In the case of conflict resolution, who is responsible? Who, or what, can a claim be made against?
3. **Contract enforceability:** Much has been made of smart contracts’ ability to cut out the middleman, thus slashing costs and increasing security when undertaking complex legal processes. But given that smart contracts are also pure computer code, it’s debatable about whether they meet the definition of a contract in the traditional sense. In the event of a contract dispute, how enforceable would a smart contract be in a court of law? Quite simply, we don’t know. At the very least, you need to make sure all smart contracts you enter at this stage have a very clear dispute resolution process attached to them.
4. **Leaving a blockchain:** Let’s suppose a blockchain is used for the affore mentioned tolling system. What happens if the organisation decides to stop using the service that supplies the blockchain and the organisation doesnt hold a copy of the data on the ledger? There needs to be provisions and processes in place that ensure the vendor hands over all your information and a complete record of all the transactions on the blockchain that are linked to the organisation name.

- Governance

A blockchain’s governance system sets the basic rules of participation and decision making. It is the core political structure of the blockchain ecosystem and must be designed equitably. These questions are akin to the structuring of the U.S. legislature between the House & Senate, creation of the electoral college, and provisions for referendums and other political processes—all considerations for who gets to make decisions and how those people are selected.

- Blockchain is ungoverned

As with any regulated system there is need for government and control. However with blockchain No one governs the networks. Similar to stock trading, the more stocks are traded, the more their value increases, similar to crpto currency the more it is traded, the more the value of that cryptocurrency increases. Since every transaction in a network is anonymous and cryptocurrency isn’t governed by anyone, blockchain has become infamous for aiding in money laundering, selling weapons or drugs, and other traditionally black-market-aided transactions. However the inherent distributed nature of the system disallows any centralized regulation. This can be a problem for a system that seeks to achieve centralised regulation and government, leaning into a technology that is mired by issues such as this would breed public distrust and reduce buy in from the public as well as regulators themselves.

- Problem with governing

Even if blockchain tech was modified to allow for centralized regulation… there would still be problems. If all countries have different approaches to titles, ownership, contracts, and transactions, how can a unified set of rules or laws be brought to fruition? If any disputes over previous transactions are made, who is the governing entity responsible for resolving this conflict? Since blockchains are immutable, how would societies handle a blockchain that adheres to modern regulations but fails to comply to unknown future regulations? This is where a lot of experts fall silent with the technology and have not encountered a technology with consequences this far reaching without a simple go to correct answer.

- Identity

As with many blockchain problems, a major preliminary hurdle is how to best define identity within the ecosystem. Provisions for government services often require personal identification. Identity politics are often the root of inequality, and leveling the playing field from the beginning is necessary for the inclusion and protection of minority communities. How does one verify their identity in each ecosystem? If it requires verifying one’s ethnicity or one’s religious or sexual preference, it could endanger those already at threat of persecution.

- Access

Just as identity is important for accessing goods and services, so too do design principles greatly effect one’s capabilities for participating in an ecosystem. The ‘digital divide’ was studied heavily in the years following the advent of the internet, and social scientists determined that those without access to new technologies experienced worsening degrees of inequality compared to those who did. Today, it is not enough to simply guarantee access to technology—it must be designed for ease of usability for those who are not technologically literate. Blockchain and digital currency are undoubtedly a complicated phenomenon with a significant learning curve for anyone who has never been exposed to concepts of public & private keys, 2FA, and other basic requirements for participating.

- Enabling of criminal activity.

Blockchain is well known for its anonymity and "enabling" criminal activities. Bitcoin bieng the case inpoint has had its root long running in anonymouse drug deals on the dark web. Notwithstanding this fact there is hope in that anonymity is not guaranteed as addresses and transactions can be traced back to the original sender and action can be taken. However this requires a lot of dedication and resources. However the large number of transactions that pass through the Ethereum network and the 15 second average block-time makes it difficult to inspect transactions. Bringing such a technology full scale to a nation may bring to light this property of ethereum and it may ganner the interest of criminals in supporting and using the blockchains anonymous nature to push their illegal activity under the guise of valid transactions on the network, bypassing government regulation and authorities. 

# Doubts

- Exposure

Replacing established processes and systems with a black box can be disconcerting to a lot of users, especially when involved in moving large assets. Some people want to see and understand how blockchain technology is replacing their previous processes. In order to create trust in the new technology, the user needs to understand and see how the application processes work. It is important to help the user understand how blockchain is working for them to improve their processes, such as data visibility, audit trails, and provenance.

- Trust

When dealing with highly sensitive data, maintaining the user’s trust is critical. Users must perceive the applications to be reliable, trustworthy, and stable. This is accomplished through data exposure, consistency, feedback, and active guidance. Designing this into the system means providing the user with clear feedback and active guidance through the task at hand.

- Performance

A blockchain transaction only gains validity once forged into a block. Due to possible occurrences of side-chains it is usually considered safe to wait for a few more blocks to be forged after the block your transaction is in. For Ethereum, this wait is for about 4-6 blocks – which is about 2 minutes – until a user can be sure that the transaction is valid and final. This is fine for a financial transaction in an online world, but would prove to be a hurdle within a distributed system that caters for high volume of vehicles crossing toll gates and toll booths. This trade-off for time brings in an assurance that the payment went through and cannot be revoked or reversed as the blockchain is immutable. Time can be differentiated into various categories:
**Time to transaction:** The time it takes for your transaction to arrive in the system.
For nearly any transactional system nowadays, this is usually quite instant. For decentralized networks, it would be quite instant that one node gets the transaction, this is not a guarantee that the transaction will be ever fulfilled, e.g. a node could simply accept transactions but never forward it.
**Time to transaction receipt:** The time it takes to have a solid proof that you entered your transaction.
For example, if you transfer money from your bank you could instantly print out a receipt which is usually good enough for a proof that you transferred the money. For blockchain, this would be the first time your transaction appears in a block, which might take up to 30 seconds, depending on the frequency of new blocks and the number of transactions waiting for a block.
**Time to fulfillment:** The time it takes to have a successful fulfillment of a (business) transaction.
Even if you have the receipt, the money is not yet on the bank account of the recipient. This usually takes hours or days. Here, the blockchain has advantages because once a transaction is in a block, the transaction is usually fulfilled. However, it is usually considered safe to wait up to six blocks to treat a transaction as successful, which could take up to 2 minutes. Traditional integrated transaction systems can usually be much faster (milliseconds to seconds) – but there are often batch-jobs going on (waiting for thousands for transactions to move it over to the next system) or sometimes even manual steps in between which leads to days.
**Time to fulfillment receipt:** The time it would take to get a receipt back, that the recipient really got the money.
This is usually not done in a bank transfer scenario nowadays, but as a sender you usually want some proof that the money was received. Here blockchain really has an advantage.
All these factors show a simplified business view on performance of transactions. A blockchain reduces the number of parties involved in a transaction, the more parties are involved in a process, the more time you can save with a blockchain. However, it might make sense to think about the implemented scenario first and if it could be handled by better integrating the systems or lifting restrictions. If only one or two parties are involved, integrated systems are usually much faster. However when we think a little bit more technical, the overhead of a distributed network (synchronize nodes, establish connections, transfer data, get consensus) can be quite a performance bottleneck.

- Revocability: 

Users are used to support and reversing things they have done wrong. A big factor in the business world is usually revocability. If errors or abuse occur, you often need to revoke or abort a transaction. This can be done by calling a support hotline, like disabling fraudulent credit cards. But this is no longer possible the same way with blockchains. Even further, it should be not possible because you are anonymous in a blockchain – once you would need support you would most probably need to open up your transaction history because otherwise the best support could not help you. Here blockchain has the biggest disadvantage as there is no reversal or revocability within the system If the error level within the system is high it would be best not to use a blockchain as the backbone of the system. Another interesting case would be the other way around: What happens if an official court tells you to change something which you can’t change anymore because it is in the blockchain? Could somebody sue you because you are technically not able to give back assets?

# Concerns

- Mutability 

Is the assurance that actors in the ecosystem cannot change the historical record. If immutability is not needed, there are simpler methods to ensure other attributes (i.e., that data has not been changed from its original form) than blockchain. It is important to consider this as it is one of the conerstones of blokchain technology. in the event that a user needs to remove a record in the blockchain or correct a mistake, this becomes impossible because Blockchains are append-only, so they will not allow for that. This may clash with Jurisidction laws because, GDPR with its "right to be forgotten" may make storing personal data of an EU national who is a truck driver paying tolls on the system on a blockchain challenging/impossible.

- Trust

Are there multiple actors involved within the system or is the system deployed and controlled by a single organisation. Trust can be bypassed if the solution is to be deployed within an organisation but the moment we step out into the wild, it becomes a different story. Since the use case has multiple actors who do not trust each other and may gain / benefit from exploiting each other then using blockchain becomes a good solution to cater for trust. Blockchain also provides transparency provided where all participants can see the chain (even if individual transactions may be anonymous). Many organisations as well are used to services such as escrow or notary services adn auditors to validate or audit transactions. This makes it possible to adapt the entire organisation and other parties to a new "transaction verification" system and "mining".

- Identity

How important is it to know the humans or systems involved in a transaction to be able to ensure that transactions cannot be counterfeited or compromised. Application of Blockchains are useful where actors want to know the identity of participants in a transaction (e.g., which vehicle travelled through which route with which cargo). Blochchains make it possible for identities of parties to be immutable and verified on the blockchain, coupled with the immutability of transactions make it a secure and verifiable trasnaction store through merkle-patricia tries.

- Distributed Architecture

A vehicle tolling system may be necessary to have fail-over and be always avaialble as in developed and developing countries roads are never empty. The blockchain by design is distributed and any actor with computing power can become a node. This makes it possible for the vehicles themselves to participate as well as the toll booths as well. Distributed architecture brings with it system reliability from node failures, immunity from the actions of a minority of bad actors, and security and integrity achieved by having multiple participants confirm transactions and achieve consensus.

- Perfomance

There are considerations regarding how efficient the payment system has to be. How quickly must transactions be processed, how many transactions can be processed per second and can the  blockchain meet the needs? A blockchain is computationally expensive and can only support a limited number of transactions per second, 15 seconds trasnaction time in the case of Ethereum. It is important to make 

- Devices & Access

How will users access and interact with the Blockchain. How powerful are the devices and what sort of information do they access and how often. Do constrained devices with limited resources need to participate as a node in the blockchain? This is key because the amount of time a user has to wait in order to connect and interact with the network can quickly become a huge limiting factor and often leads to technology abandonment. Ethereum wins within this category because it enables fast sync which can be used by light clients that need to just summarise and present information and not replicate the entire chain, however this may change with more transaction data bieng held within the system.

# Problems

- 51% Attacks and Double Spending

Since blockchains are just nodes working together to create a network. One of the beauties of this is that ownership is anonymous. This is a double edged sword as the power of bitcoin can be summased to computing power. If a group of individuals is able to ammass 51% or more computing power on the network thiings can go wrong. One of the worst case scenarios of a 51% attack is double spending, when a unit of digital currency is spent twice. This would equate to someone driving through the toll system at no cost or even large shipping conglomerates (backed by their recent investment in computing power) shipping large quantities at absolutely no cost.

- Cost Efficiency

The development effort and infrastructure required to build this solution.
The cost in terms of actual labour, expertise, man hours and financial input required to develop, test, deploy and maintain such a solution would probably be high because there are a few domain experts within building large scale enterprise blockchain based systems. The availability of talent affects costs as well as maintenance and the longevity of a blockchain solution as the industry and technology evolve with continued innovation.

- Performance

Due to the high traffic within a road toll system, there is need for high throughputs and as there will be high transactions bieng processed per second. If there are bottle-necks in trasnaction processing there maybe problems encountered as this leads to long lines, backed up traffic and general distrust in the system by the public who need to have the highest level of buy-in in order for the system to be a success.

- Flexibility & Coexistence

There needs to be a high level of interoperability and data exchange between the blockchain and other 3rd party systems. Regular users of the system will not probably be able to decode and follow their trasnactions on etherscan on a daily basisi, hence they need to be able to call and view all this data on interfaces they are used to. Enterprise level users should be able to compile data, aggregate it and use it for reporting. The blockchain network needs to be able to coexist with the rest of the enterprise, network participants, and adjacent systems, which may have overlapping and complementary functions. The blockchain transactions should be able to plug in and out of current financial systems as well as in rare cases other blockchains.

- Longevity of the solution

As a community or country develops or the organisation in charge of the system grows, they aspire to build a trusted network, a stable systemand ensure they can sustain the cost and operation of the network so that it can grow and scale to accommodate additional participants, requirements with changes in technology and higher volume transactions.

- Regulatory compliance 

Compliance issues are closely tied to transaction processing and can include events such as industry-specific reporting and analysis for business workflows and tasks, both automated and human-centric. Standards are critical, not only in helping to standardize a shared technology stack and deployment, but also in establishing an effective communication platform for industry experts to use for problem solving. Standards make low-cost, easy-to-consume technology possible. Large scale solutions tend to rely on technology and industry-specific standards for their successs, in the case of open source publicly available networks there is a trade-off between security, control and standardisation. looking at the recent fork in Ethereum classic and Ethereum we see that the enterprise would not have the ability to influence or stop such a thing happening and this would directly affect a live application running on the public network.

- Predictable costs of business growth

Business growth depends upon predictable metrics. Historically, a lot of industries have focused on transactions per second, but that measurement differs from system to system based on system design, compute costs, and business processes.

- Financial viability of technology vendors

Long-term support and the longevity of the deployed solution is another key problem area. There should be a sustainable vendor who can deploy updates, see to user issues and do a substantial amount of hand-holding until users mature. There will be issues to do with finding a partner or vendor who is trusted and who wont wake up one day and steal all the ether within the system. This ties into legal concerns and jurisdiction issues as well as assurance that the solution will work in the foreseeable future as it does now.

# Blockchain Solutions

- Blockchain Breeds Credibility

The subjective monetary value of cryptocurrencies make blockchain technology less prone to corruption, because it runs on credibility. A bank can make any changes to its own ledger or be at risk for hacked changes to its ledger without any of the bank’s users becoming aware. In the case of blockchain, humans only value cryptocurrency if they trust that the transactions are true. Since blockchains publicly share all transactions with the nodes in the network, transparency breeds credibility; which directly gives cryptocurrencies their monetary value. Corruption is disincentivized in a decentralized network. A 51% attack is also highly unlikely to happen within a well established blockchain such as Ethereum because it becomes harder and harder to hash an alternate chain, catch up to the latest nodes, forge transactions and supass the genuine nodes. This makes sense to join the network and become a genuine actor than become an attacker as the economic loss involved within a 51% attack out-weighs the economic value gained from bieng a genuine player who earns rewards through mining. Therefore 51% attack safety is in-built within the blockchain by design ensuring credibility.

- Autonomy transparency and a blueprint for financial transactions

The most obvious benefit of cryptocurrency is that it offers greater ease and autonomy for financial transactions. Without a third party governing monetary exchanges, cryptocurrencies allow people to transfer and transact with money, with machines and use technology between borders, nationalities and countries, with more privacy and ease than ever before. Even further, in a country where the currency is hurting it’s people (case in point the Euro in Greece), an unregulated form of currency could actually prove to be quite beneficial for the economy at large and ensure the long term use of the system is stable. No centralization and no government intervention on cryptocurrency means that control over the currency could be entirely up to a network of regular citizens and actors within the system. In this aspect, cryptocurrency is a libertarians dream.

- Benefits baked into blockchain technology design
1. Permissioned/Private. Writing records is exclusive to members; third parties can be granted read access, with the general public excluded. The permissions architecture goes beyond “access = everything” and allows third-party access to specific raw data, as deemed appropriate, for interoperability and application requirements.
2. Decentralized/P2P. Allowing for equal control over the shared database among all permissioned participants and of equal importance; distributing the number of full copies of the ledger to maximize the probability that there will always be a complete record in existence and available for those with permissions to access.
3. Immutability & Data Integrity. Records are guaranteed to be cryptographically secure, with no possibility for bad actors to threaten data integrity.
4. Scalability. The ability to secure trillions of transactions or records without compromising the networks synchronization, security, accessibility or data integrity.
5. Security. Support for data encryption and the management and enforcement of complex permission settings for participants and third parties.