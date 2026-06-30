## Starter for Ritual workshop on 23th June 2026

/hardhat -> Where we'll write the smart contract

/web -> Where the frontend lives.
# Privacy-Preserving AI Bounty Judge (Ritual Chain Workshop)

This repository contains a mobile-optimized smart contract implementation designed for the Ritual Academy assignment. It deploys a secure **Commit-Reveal** workflow tailored for decentralized, privacy-preserving AI bounty judging inside Ritual TEE environments.

## Architecture & Features

The architecture ensures that participants can submit their code solutions and AI model answers without exposing their intellectual property prematurely on-chain.

- **Cryptographic Commit-Reveal Flow**: Submissions are hidden during the evaluation phase using `keccak256` hashing functions to eliminate plagiarism.
- **Ritual-Native Hidden Submissions**: Prepares batch execution payloads formatted to trigger distributed LLM grading routines across off-chain networks.
- **Mobile-First Dev Environment**: Fully configured and compiled under isolated mobile Linux environments using `Termux` and local development nodes.

## Smart Contract Details

The contract is named `PrivacyBountyJudge.sol` and implements four core functions required to manage the lifecycle of decentralized AI bounty programs:

1. `submitCommitment(uint256 bountyId, bytes32 commitment)`: Allows users to lock their encrypted cryptographic hash.
2. `revealAnswer(uint256 bountyId, string calldata answer, bytes32 salt)`: Decrypts and verifies the data integrity on-chain via verification formulas.
3. `judgeAll(uint256 bountyId, bytes calldata llmInput)`: Routes batch payloads directly into secure execution components.
4. `finalizeWinner(uint256 bountyId, uint256 winnerIndex)`: Locks and stores the winner's immutable index parameters.

## Deployment Environment

- **Node Setup**: Local blockchain orchestration and client state testing completed via isolated phone containers.
- **Compiler Options**: `solc v0.8.20` optimization passes.
