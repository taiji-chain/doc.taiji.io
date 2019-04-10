---
title: "General Data Protection Regulation"
date: 2019-04-10T09:35:18-04:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
reviewed: true
---

The GDPR consists of 99 articles and about ten are related blockchain technologies. Seven of the ten articles are to be implemented using conventional methods. 

* Article 2 refers to the scope of the GDPR, namely the fully or partially automated processing of personal data.
* Article 5 sets out some principles for processing the data, such as the lawfulness and traceability of the processing, or that the data was collected for specified, explicit and legitimate purposes.
* Article 18 deals with the right to restrict processing.
* Article 20 requires that the stored data be sent in a machine-readable format either directly to the person concerned or, if that is their wish, to a third party.
* Article 21 refers to the right of appeal of data subjects. They may object to processing at any time, for reasons that arise from their particular situation.
* Article 22 allows data subjects to request a decision not based on automated processing, provided that it significantly affects them.
* Article 25 requires the processor to take appropriate technical and organizational measures to implement data protection principles and to make data protection-friendly pre-settings.
* Article 32 states that responsible persons shall take appropriate technical and organizational measures to ensure a sufficient level of protection of the data; adequate means here appropriate to the risk.


For Blockchain projects there are three articles of the GDPR left, for which you need different solutions:

Article 16: Right to data update
Article 17: Right to forget
Article 32: Protection of personal data

### Overview of the articles

The right to data update in Article 16 describes the possibility to update data. It must be possible to replace an old, wrong record with a new one. Depending on the design, this means the deletion of the old data; To be on the safe side, you stick to this strictest interpretation. In their case, the implementation on the Blockchain is not trivial due to the immutability of existing data, but is anyway due to implement Article 17.

Article 17 describes the right to forget. It is often used to prove the impossibility of a DSGVO compliant blockchain application; Finally, data manipulation security is one of the main arguments for blockchain techniques. In the example implementation, the author shows some ways to accomplish these and the two previously described requirements. The approach consists of the three components Hash, Secret and Merkle-Tree (hash tree); This procedure can be combined with zk-SNARKs as the fourth component.

In this case, no personal data is stored directly on the blockchain, but linked with the individual components to an off-chain database. The construction described below proves the correctness of the data without third parties gaining unwanted access.

Article 32 deals with the protection of personal data. The aspect has a special blockchain relevance, since public chains make all the data publicly available. Consequently, protection needs special attention.

More information can be found at https://translate.google.com/translate?sl=auto&tl=en&u=https%3A%2F%2Fwww.heise.de%2Fdeveloper%2Fartikel%2FBlockchain-und-DSGVO-muessen-kein-Widerspruch-sein-4337924.html%3Fwt_mc%3Dsm.share.mail.link
