#Contracts

##Intro (contract) _undependable_
- Is the access point to the platform
- Has access to a registry of the projects associated to each user
- Points to the _Deployer_ contract
- Is controlled by a trusted entity for now. Will be controled by a _Governance_ contract in the future
- There is only one
- Is for UX only. Rest of the contracts don't depend on it

##Deployer (contract) _undependable_
- Deploys all the contracts that will form a project
- Is controlled by a trusted entity for now. Will be controled by a _Governance_ contract in the future
- Rest of the contracts don't depend on it, but is a trusted contract that facilitates the work.

##Directory (contract) _dependable_
- There is one per project
- It serves the same purpose as a proxy contract.
- It is used to be able to update the rest of the contracts
- It returns the contract address associated to an id
- _Governance_ contracts rely on it to get
- Has a _Governance_ contract associated
- Only the _Governance_ is allowed to updated the directory

##IGovernance (interface)
- Is the signature interface for all _Governance_ contracts

##Governance (contract)
- Implements _IGovernance_
- Handles the voting
- Has a _Merit_ contract associated
- Only one _Merit_ contract can be used by a _Governance_ contract
- _Merit_ is updated via the _Directory_ contract
- A project may have multiple of them to handle different areas (funding, proposals, game rules...)

##IMerit (interface)
- Is the signature interface for all _Merit_ contracts

## Merit (contract)
- Implements _IMerit_
- Defines the voting rights of an address
- Multiple _Governance_ contracts may use the same _Merit_ contract





