# OMA3 Soulbound Token Litepaper

## 1. Executive Summary

OMA3 is a Web3 industry alliance, structured as a consortium, with the goal of ensuring an interoperable and user-owned metaverse. The consortium structure is one of the most proven mechanisms to enable industry collaboration, but consortiums are only as good as the quality of member contribution.  Encouraging, tracking, and rewarding member contributions has always been a challenge in any industry collaboration and consortiums are no different.  To solve this challenge, OMA3 is incorporating DAO elements into its governance.  This paper is our first step to creating a more effective collaboration structure for Web3.

Over the past few years Web3 projects have experimented using tokens to reward contribution or track reputation, expanding the utility of tokens beyond the more well-known use cases such as store of value and monetary transactions.  OMA3’s token architecture builds on such projects to enhance the usefulness of tokens in the context of collaboration. 

The primary purpose of the OMA3 token architecture is to track the reputation and contributions of consortium members.  The primary component of the architecture is a “soul-bound” non-fungible token (SBT).  An SBT is a non-fungible token (NFT) that cannot be transferred.  One SBT is allocated to each member and is included as part of membership.  The SBT stores the member’s OMA3 reputation. These SBTs are also used for tracking votes, as consortiums overwhelmingly use a “one member/one vote” form of governance. This is in contrast to many Web3 DAOs which use “one fungible token/one vote” governance.Currently OMA3 has no plans for a fungible token.  Further development of the OMA3 token architecture will happen within OMA3’s working groups.

Reputation is the most important metric in OMA3’s token architecture and reputation can be earned by contributing to OMA3 in various ways.  Reputation can also be lost under certain circumstances.  Reputation determines the privileges each member is granted by OMA3, including co-marketing, recognition, and any other benefit OMA3 may decide to bestow in the future.  One of the biggest drivers of reputation is OMA3’s bounty system.  Members can use the OMA3 bounty system to propose work that needs to be accomplished by OMA3, and members can apply to do the work described by the bounty.  Bounty award decisions are made initially by OMA3 leadership, and member reputation plays a big role in this decision-making process. Over time bounty award decisions will become more decentralized.

The purpose of this paper is to lay the foundation for OMA3’s token architecture, and be a starting point for the remaining work that will be accomplished in OMA3’s new Token Working Group (TWG).  It is expected that the TWG will change some of the content in this paper.

## 2. Background

### 2.1 OMA3

OMA3 is an industry alliance structured as a Swiss association.  The goal of OMA3 is to create specifications, software repositories, and infrastructure that enable the interoperable, user-owned metaverse.  

OMA3 is governed like a typical modern industry consortium.  Details on this governance framework are located in the [OMA3 Organizational Documents](https://assets.website-files.com/62a88c8ec868deb8bcfa3353/63611fb302b730108a90e482_oma3-complete-signable.pdf).  To summarize, OMA3 has three tiers of member participation:

  * Community Member:  This is the most accessible membership level with benefits that include invitations to the OMA3 Discord channel, membership SBTs, rights to future airdrops, and rights to review and comment on OMA3 work products before they become final.  OMA3 has yet to activate this membership level as of March 20, 2023.

  * Creator Member:  Creator Members receive all the rights of Community Members, plus participation and voting rights in OMA3 working groups as well as the right to be nominated to OMA3 leadership positions such as working group chairs.  This membership level is open to any organization.

  * Sponsor Member:  Sponsor Members receive all the rights of Creator Members, plus the right to nominate one individual to the OMA3 Board of Directors as a voting member.  Sponsor Members are elected by the OMA3 Board and reputation plays a large role in this election.

Consortiums are responsible for creating some of the most widely used technologies in the world, but there is a “tragedy of the commons” in consortiums wherein members are incentivized to let others do the work of running working groups, creating specifications, and writing code because all members benefit the same regardless of whether they do the work or not.    OMA3 intends to change these incentives by rewarding members based on their contributions, thereby encouraging members to do the necessary work.

### 2.2 Stakeholders

#### 2.2.1 Leaders

OMA3 leaders are individuals who have added OMA3 governance responsibility beyond the responsibilities of other member representatives.  Leaders include OMA3 officers (Chairperson, Secretary, Treasurer, Vice Chairs, and other roles held by OMA3 representatives), working group leaders (chairs, co-chairs, project managers, and open source maintainers that are members of OMA3), and committee leaders (Sponsor Member representatives that run board-level committees).  Current leaders can be found at [OMA3.org](https://www.oma3.org).

#### 2.2.2 Employees

OMA3 employees include staff directly hired by OMA3 such as Executive Director, CTO, CMO, and operations director.  These positions can be occupied by member employees or be individuals employed directly by OMA3.

#### 2.2.3 Service Providers

OMA3 members can provide services to OMA3, and if these services are provided at a discount these discounts can be tracked in the member’s SBT.  Service providers include consultants, contractors, accounting firms, marketing and PR firms, attorneys, and event planners.

#### 2.2.4 Implementers

Implementers include any organization that uses the work product of OMA3 to build and/or offer products and services, including developers, exchanges, and wallet providers.  Implementers can be members or non-members, but only member implementers receive benefits from OMA3.

#### 2.2.5 Users

Users are individuals who are not OMA3 members, yet still use products or services that incorporate OMA3 work products.  In the future, individuals will also be able to join OMA3 as members.

## 3. Soulbound Membership NFT

### 3.1 SBT Structure

Each OMA3 member receives an SBT that is non transferable.  Which chain(s) OMA3 SBTs reside on will be determined in the future.  

To protect OMA3 operations, SBTs are controlled by wallets sanctioned by OMA3.  OMA3 enforces security and access control requirements for SBT wallets.  Access control requirements may be different depending on the level of membership.  Each SBT wallet must be stored on an OMA3-approved multi-sig wallet which requires at least two signers for every transaction signature.  Individual multisig signers must also use an OMA3-approved wallet. The complete list of such wallets will be composed and published in the future.

KYC checks will be used for all corporate and individual signers.  Details on KYC will be worked out in the TWG.

The OMA3 SBT is compliant with the W3C Decentralized Identifiers (DID) specification:

  * DID Verifiable Credential (“VC”)- The DID VC is the software object that is the actual identity credential.  In the OMA3 token architecture, the VC is the OMA3 SBT.
  * DID User- A User in the W3C specification is the entity that is represented by the VC.  In the OMA3 SBT model, the DID User is the OMA3 member
  * DID Issuer- An Issuer in the W3C specification is the entity that gives out the VC and vouches for the authenticity of the VC by signing it.  With OMA3 SBTs, OMA3 is the Issuer.

Currently, it is not intended for OMA3 SBTs to store private information, so the privacy-preserving characteristic of DIDs is not implemented at this moment.  There are no existing Verifiers besides OMA3, although this is expected to change as OMA3 grows.

### 3.2 SBT Functionality

An OMA SBT stores the following data (see Figure 1):

  * Identity
    * Member name and unique ID
    * Current official representatives
    * Affiliates that are also OMA3 members (if any)
  * Membership
    * Changes in membership status, including the new membership level (Sponsor, Creator, Community, or Non-Member) and the time of status change
    * Membership fees paid and date of payment
  * Participation records
    * Meeting attendance (Working groups, committees, General Assembly, Board of Directors)
    * Representing OMA3 at events
    * Official comments on draft working product (e.g.- comments on specifications)
    * Voting records
  * Contributions
    * Contributions within the OMA3 Bounty System (see below)
    * Monetary contributions beyond membership fees
    * Time spent by OMA3 Leaders (see Stakeholders above) on OMA3
    * Fee discounts on services (e.g.- providing web development services)
    * Other contributions approved by OMA3 that have monetary value
  * Adoption Metrics (TBD based on working group recommendations), for example:
    * Gas fees paid using an OMA3 smart contract
    * User referrals
    * Fees for using OMA3 infrastructure

![Figure 1](https://github.com/oma3dao/public-documentation/blob/main/token/diagram-1.png)
**Figure 1: Soulbound Token Usage**

## 4. Bounty System

### 4.1 Bounty transactions

Bounties are opportunities for members to earn reputation and privileges by contributing to OMA3.  There are two types of bounties:  bounties governed by the Board (“Board Bounties”) and bounties governed by the Board and Working Groups (“Working Group Bounties”) (see Figure 2).  There are two ways to earn reputation with bounties:

  1. Create a Board Bounty:  Submit a proposal to create a bounty for fulfilling a board-level need such as creating a working group or a creating topic for a working group to address.  Members that submit Board Bounty creation proposal(s) that end up getting approved by the Board will receive a reputation reward. The reward for submitting a Board Bounty creation proposal is the same for each bounty creation proposal.  If proposals are very similar, only one will be approved.  Bounty proposers may recommend a reward for members that fulfill the bounty, but proposals to fulfill the bounty can set their own reward which may be different from the recommended reward.  Creating Working Group Bounties do not earn rewards because they are proposed by the working group chairs, and chairs already earn reputation for leading working groups.

  2. Fulfill a bounty (Board or Working Group):  For any open bounty, a member may submit a fulfillment proposal (e.g.- nominate for a leadership or individual contributor role, submit a document, write code, etc.).  The fulfillment proposal may indicate acceptance of a bounty fulfillment review process (see below). If conditions permit, the Board or working group may approve multiple fulfillment proposals for a bounty.

### 4.2 Bounty fulfillment selection process

Board Bounties are initially awarded by the Board.  The Board takes into account the following factors when rewarding a bounty:

  * Capability of the member submitting the fulfillment proposal
  * The nature of the work for the bounty (e.g.- creating a specification)
  * Proposed reward for fulfilling the bounty
  * Reputation of the members submitting the fulfillment proposal, as stored in SBTs
  * Collateral (“stake”) put up by the fulfillment proposers that can be lost if the proposers are unable to deliver.

Working Group Bounties are decided by a vote in working groups, but the vote must also be ratified by the Board.  

![Figure 2](https://github.com/oma3dao/public-documentation/blob/main/token/diagram-2.png)
**Figure 2: Bounty Process**

## 5. Allocation of OMA3 Benefits

Member companies contribute to OMA3, in working groups and outside of working groups, and these contributions are recorded in member SBTs.  Some of these contributions include monetary contributions, work done by member employees in a leadership position, or contributions in-kind.  

Bounties also accrue reputation in SBTs.  When bounty rewards are issued (either for creating a bounty or fulfilling a bounty) a contribution with a monetary value attached is recorded in the rewarded member’s SBT.   

OMA3 benefits are allocated in an objective manner, based on multiple transparent mechanisms for gaining reputation.  One reputation metric is attendance in meetings.  Members that attend more meetings receive proportionally more attendance reputation than members that do not.   

### 5.1 Contributions based on monetary value

Another metric is based on the monetary value of a member's contribution. Most contributions to OMA3 can be valued in monetary terms, which makes the relative value of each contribution easy to calculate, and the most prevalent type of monetary value based contribution comes in the form of the Bounty System (see Section 4).  Non-bounty contributions are as follows:

  * Currency contributions
    * OMA3 may request additional funds from its membership beyond the annual membership fee. Such contributions are voluntary and are tracked in each member’s SBT.
    * Web3 investors who wish to fund OMA3 must do so as a member contribution in accordance with this allocation.
  * Officer/Working group chair compensation
    * Officers and working group leaders accrue reputation for contributing time to OMA3. The value of this time is based on hours and an hourly rate and is tracked in a member’s SBT.
    * Time spent in working group meetings and Board meetings do not count as a contribution.
  * Service provider compensation
    * Service providers can accrue reputation for providing service at a reduced rate.  
    * Service providers that accrue reputation must become a member of OMA3 (any membership tier).
    * Service provider contributions are tracked in the service provider’s SBT.

### 5.2 For Future Work

Unlike most DAOs, OMA3 does not use a fungible token to determine voting influence.  Governance voting in OMA3 is based on a one member/one vote policy, hence the SBTs. The TWG will need to further refine the mechanics of the OMA3 token architecture in working group meetings.  The following are some of the many areas that need more investigation by the TWG. 
 
#### 5.2.1 Bounty Completion Review process

Some bounty rewards pay out over time, not all at once.  For example, a large software project may pay rewards on alpha, beta, and production milestones.  Infrastructure may require a long period of production use before final rewards get paid out.  The payout schedule is up to the bounty.  For example, 50% of a bounty reward may be paid out on project completion and 50% may be held back pending a review of project performance.

#### 5.2.2 Losing reputation

A member’s reputation can be lost in certain situations.  There will also be a process to dispute reputation loss in some cases.  These details will be worked on in the TWG. 

#### 5.2.3 Privacy

Members may not want some of the data stored in SBTs to be available to the public.  Members may not even want the data to be available to other members.  The Token Working Group will specify the correct privacy preserving mechanisms based on the nature of the data and the level or privacy needed

## 6. Legal Considerations

OMA3 is fully aware of the regulatory environment and recent enforcement actions against several Web3 projects.  Design and implementation of this OMA3 token architecture may need to change based on the resolution of these actions or guidance given by regulatory agencies and legislative bodies.  However, OMA3 believes in the value this token architecture brings to both OMA3 and the Web3 metaverse as a whole.  We are committed to realizing this value in a regulatory compliant manner.

## Authors

### Mohamed Ezeldin
**[Animoca Brands](https://www.animocabrands.com)**, Tokenomics Team Lead   
**OMA3**, Token Working Group Chair


### Jerry Lai
**[Animoca Brands](https://www.animocabrands.com)**, Tokenonics Team   
**OMA3**, Token Working Group Vice Chair


### Alfred Tom
**[Wivity](https://www.wivity.com)**, CEO  
**OMA3**, Acting Executive Director

## About OMA3
[www.oma3.org](https://www.oma3.org)   
[@oma3dao](https://www.twitter.com/oma3dao)   
[https://www.linkedin.com/company/oma3/](https://www.linkedin.com/company/oma3/)   

## Public Comments
Create an issue on Github:  [https://github.com/oma3dao/public-documentation/](https://github.com/oma3dao/public-documentation/)   
Comment in [Google Docs](https://docs.google.com/document/d/1z6nI7sHTbK5_8Y43xEuoy21kg3ZikcKwJopagSzb4ko/)    
