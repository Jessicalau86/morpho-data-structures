# Morpho Data Structures 🦋

This repository contains the data strcutures that can be used for the matching engine.
The goal is to compare them in terms of security and gas consumption to find the best solution for the protocol and its users.

## Data structures

The data structures we implement and modify are based on public works of amazing developers. We thank them for what they have done 🙏

### Double Linked List

The current implementation of the double linked list is based on this [article](https://hackernoon.com/a-linked-list-implementation-for-ethereum-deep-dive-oy9432pa) written by Alberto Cuesta Cañada.
You can find the repository [here](https://github.com/HQ20/contracts/tree/master/contracts/lists).
Note that the code has been modified to meet our needs and to allow us to sort the double linked list.

### Red Black Binary Tree

A [Red Black Binary Tree](https://en.wikipedia.org/wiki/Red%E2%80%93black_tree) is a kind of binary tree that allows insertion / deletion / search in `O(log(n))`.
Our implementation is a modified version of the [OrderStatisticsTree repository](https://github.com/rob-Hitchens/OrderStatisticsTree) written by [Rob Hitechn](https://github.com/rob-Hitchens) which is also based on [BokkyPooBahsRedBlackTreeLibrary repository](https://github.com/bokkypoobah/BokkyPooBahsRedBlackTreeLibrary) written by [bokkypoobah](https://github.com/bokkypoobah).
Our modified version makes keys unique items instead of just (key, value) unique pairs.

You can refer to the following table for the complexity of some data structures.

![complexities](https://devopedia.org/images/article/17/7752.1513922040.jpg)

### Other data structures

Other data structures may be explored in the future.

## Contributing

In this section, you will find some guidelines to read before contributing to the project.

### Creating issues and PRs

Guidelines for creating issues and PRs:

- Issues must be created and labelled with relevant labels (type of issues, high/medium/low priority, etc.).
- Nothing should be pushed directly to the `main` branch.
- Pull requests must be created before and branch names must follow this pattern: `feat/<feature-name>`, `test/<test-name>` or `fix/<fix-name>`. `docs`, `ci` can also be used. The goal is to have clear branches names and make easier their management.
- PRs must be labelled with the relevant labels.
- Issues must be linked to PRs so that once the PR is merged related issues are closed at the same time.
- Reviewers must be added to the PR.
- For commits, we use the [conventional commits pattern](https://www.conventionalcommits.org/en/v1.0.0/).

### Before merging a PR

Before merging a PR:

- PR must have been reviewed by reviewers. The must deliver a complete report on the smart contracts (see the section below).
- Comments and requested changes must have been resolved.
- PR must have been approved by every reviewers.
- CI must pass.

For smart contract reviews, a complete report must have been done, not just a reading of the changes in the code. This is very important as a simple change on one line of code can bring dramatic consequences on a smart contracts (bad copy/paste have already lead to hacks).
For the guidelines on "How to review contracts and write a report?", you can follow this [link](https://abiding-machine-635.notion.site/Solidity-Guidelines-7c9a201413df47d6b72577374f93a697).

By default, PR are rebased with `main` before merging to keep a clean historic of commits and the branch is deleted.

## Testing

First, install dependencies with:

```
yarn
```

To run test, you can run:

```
yarn test
```

For coverage, run:

```
yarn coverage
```

## Code Formatting

We use prettier with the default configuration mentionned in the [Solidity Prettier Plugin](https://github.com/prettier-solidity/prettier-plugin-solidity).
We recommend developers using VSCODE to set their local config as below:

```
{
"editor.formatOnSave": true,
"solidity.formatter": "prettier",
"editor.defaultFormatter": "esbenp.prettier-vscode"
}
```

In doing so the code will be formatted on each save.

We use Husky hook to format code before being pushed to any remote branch to enforce coding style among all developers.

## Questions

For any question you can send an email to [merlin@mopho.best](mailto:merlin@morpho.best) 😊