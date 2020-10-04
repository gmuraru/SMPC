# 1. Introduction

Introduced by [*Andrew Yao*](https://iiis.tsinghua.edu.cn/yao/) in the 1980s as a toy problem (Yao's Millionaires Problem):

*Suppose 2 billionaires want to find out which one of them is richer, but they don't want to disclose any other information (like how much money they have)"* &mdash; Compute X1 < X2 on private data

**Properties:**

- *secure computation* &mdash; perform computation on private data and keep that data secret
- *verifiable computation* &mdash; allow the parties to confirm that what they get is really the function output on their input

## 1.1 Outsourced Computation

In the simplest scenario, let's say there are involved 2 parties: the **data owner** and the **computation provider** (has a lot of compute power). The party that holds the data wants to do computation over it and sends the encrypted data to the other party.

It does the computation over the encrypted data and sends the result (also encrypted) back. The **computation provider** does not learn anything about the data it computed over. The **data owner** can decrypt the received data, now being in posession of the plaintext output.

Types of **Homomorphic Encryption (HE)**:

- **partially-homomorphic encryption (PHE)** &mdash; only certain operations can be performed
- **fully-homomorphic encryption (FHE)** &mdash; universal set of operations

The **advantage** of HE over SMPC is that it requires less communication rounds between parties, but the **downside** is that it more heavy computationally.

## 1.2 Multi-Party Computation

It allows a group of **data owners** (they don't trust each other) to compute a function that depends on their data.

## 1.3 MPC Applications

- **Secure auctions**
  - *bid privacy* - no player should know the bid of another player
  - *bid non-malleability* - a player bid should not be used to generate another bid

- **Voting**
  - Requires the above properties - asserted by legislation
  - *coercion resistance* (not standard in MPC) &mdash; voter needs to prove to a third party how they vote (in case of bribery, vote selling)

- **Secure Machine Learning**
  - *private inference* &mdash; allow a client to run inference on a private model (on the server-side) using private input data
  - *private training* &mdash; allow more independent users to combine their (private) data to traing a model

- **Others** (which I found more interesting): privacy-preserving network security monitoring, ad conversion, spam filtering on encrypted email

### 1.3.1 Deployments

- MPC is primarly deployed as an enabler of data sharing

**Examples**:

- *Danish sugar beets auction* &mdash; between the farmers and Danisco (unique company in Denmark that processed sugar beets)
- *Estotian students study* &mdash; presumption that the IT industry was hiring too aggresively such that there was a high procent rate of students failing to graduate
- *Boston wage equity study* &mdash; identify salary inequities between various employee gender and ethnic demographics
- *Key management* &mdash; safeguard sensitive data as it being used and split key material across more servers

## 1.4 Overview

Books **focuses** on the following:

- two party scenario (one party might be corrupted)
- generic MPC tehniques