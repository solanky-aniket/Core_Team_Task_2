Simple Voting Smart Contract

 Overview
This contract enables a transparent and fair voting system between two candidates.
Each wallet address can vote only once, and voting can be controlled by an administrator.

 Ownership / Admin Logic
The admin is the address that deploys the contract.
This is set in the constructor using `msg.sender`.
Only the admin can enable or disable voting using `toggleVoting()`.

Voting Rules
Voting is only allowed when the voting status is `On`.
Each wallet address can vote only once.
Any attempt to vote again will fail due to a `require` check.
 Only Candidate 1 or Candidate 2 can be voted for.

Security Filters
 Duplicate voting is prevented using a `mapping(address => bool) hasVoted`.
 Voting status is controlled using an `enum` (`On` / `Off`).
 Invalid candidate IDs are rejected.

 Functions
 **`vote(uint candidateId)`** – Cast a vote for Candidate 1 or 2.
 **`getVotes()`** – Returns vote count for both candidates.
**`toggleVoting(bool on)`** – Admin function to start or stop voting.

 Solidity Version
 Solidity >=0.8.20


