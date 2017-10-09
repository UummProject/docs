#Contracts

##Intro (contract) _undependable_
- Is the access point to the platform
- Has access to a registry of the projects associated to each user
- Points to the _Deployer_ contract
- Is controlled by a trusted entity for now. Will be controled by a set of _Governance_ contracts in the future
- There is only one
- Is for UX only. Rest of the contracts don't depend on it

##Deployer (contract) _undependable_
- Deploys all the contracts that will form a project
- Is controlled by a trusted entity for now. Will be controled by a set _Governance_ contracts in the future
- Rest of the contracts don't depend on it, but is a trusted contract that facilitates the work.

##Directory (contract) _dependable_
- There is one per project
- It serves the same purpose as a proxy contract.
- It is used to be able to update the rest of the contracts
- It returns the contract address associated to an id

- _Governance_ contracts rely on it to get
- Has a set of _Governance_ contracts associated
- Only the _Governance_ contracts are allowed to updated the directory

## Governance (set of contract references)
 - Includes
    + _CreateProposal_: contract implementing _iCreateProposal_
    + _CreateProposalMerit_: contract implementing _IMerit_
    + _VoteProposal_: contract implementing _iVoteProposal_
    + _VoteProposalMerit_: contract implementing _IMerit_
    + _ProposalStorage_: contract holding all proposals data
    + owner : the only address that can modify a _Governance_
- _CreateProposalMerit_ and _VoteProposalMerit_ can be the same

## ICreateProposal (interface)

## CreateProposal (contract)
- Implements _ICreateProposal_
- Has a _Merit_ contract associated
- Its _Merit_ contract is updated via the _Directory_ contract
- Controls authorization to create proposal based on its _Merit_ contract

## IVoteProposal (interface)

## VoteProposal (interface)
- Has a _Merit_ contract associated
- Controls authorization to vote for a proposal based on its _Merit_ contract

## IMerit (interface)
- Is the signature interface for all _Merit_ contracts

## VoteProposalMerit (contract)
- Implements _IMerit_
- It's associated to a _VoteProposal_ contract
- Defines the voting rights of an address based on the _Merit_ contract

## CreateProposalMerit (contract)
- Implements _IMerit_
- It's associated to a _CreateProposal_ contract
- Defines the voting rights of an address based on the _Merit_ contract

##ProposalStorage (contract)
- It stores all the proposals
    





