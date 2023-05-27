# SupplyChain
The supply chain management system implemented in this project provides a transparent and decentralized solution for tracking the flow of goods or items from creation to delivery. It leverages the power of smart contracts on the Ethereum blockchain to ensure immutability, auditability, and automation of supply chain processes.


# Supply Chain Management

This repository contains Solidity smart contracts for implementing a basic supply chain management system on the Ethereum blockchain. It consists of two contracts: `ItemManager.sol` and `Item.sol`.

## ItemManager.sol

The `ItemManager.sol` contract manages the supply chain and keeps track of the different steps involved in the process. It allows the creation of new items, triggering of payments, and marking items as delivered. The contract maintains a mapping of items and emits events to track the progress.

To use the `ItemManager` contract, import it into your project and interact with its functions:

- `createItem(string memory _identifier, uint _priceInWei)`: Creates a new item in the supply chain with the given identifier and price.

- `triggerPayment(uint _index)`: Allows an item contract to trigger the payment step by sending the required amount of Ether. Only the item contract itself can call this function.

- `triggerDelivery(uint _index)`: Marks an item as delivered in the supply chain. This step can only be triggered after the payment step.

## Item.sol

The `Item.sol` contract is imported by `ItemManager.sol` and handles individual items in the supply chain. It keeps track of the item's price, the amount paid, and the item's index. When an item receives a payment equal to its price, it automatically triggers the `triggerPayment` function in the `ItemManager` contract.

To use the `Item` contract, import it into your project along with the `ItemManager` contract.

## Usage

1. Install the required dependencies and set up your Ethereum development environment.

2. Import the `ItemManager.sol` and `Item.sol` contracts into your project.

3. Deploy the `ItemManager` contract to the Ethereum network.

4. Interact with the deployed `ItemManager` contract using a blockchain client, such as Remix or Truffle, or by calling its functions programmatically using a web3 library.

5. Monitor the emitted events to track the progress of the supply chain and ensure that items are created, paid for, and marked as delivered correctly.

## Contributing

Contributions to this supply chain management project are welcome. If you have any suggestions, bug fixes, or feature enhancements, feel free to submit a pull request.

## License

This repository is licensed under the [MIT License](LICENSE).
