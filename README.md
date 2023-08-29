# TokenMap

This contract enables the listing and selling of NFT lands. It also integrates with Chainlink Oracles for additional features.

# Features

* Listing of NFTs representing lands
* Purchasing listed NFTs
* Chainlink Oracle integration for fetching geographical data

# API

## getListingPrice() -> uint256

Returns the current listing price for market items.

## createMarketItem(address, uint256, uint256, string, string)

Lists a new NFT land on the market.

* `address`: The address of the NFT contract
* `tokenId`: The token ID of the NFT
* `price`: The price of the NFT
* `CoordCenterLat`: The latitude of the NFT location
* `CoordCenterLng`: The longitude of the NFT location

## createMarketSale(address, uint256)

Allows a user to purchase a land from the market.

* `address`: The address of the buyer
* `itemId`: The ID of the NFT to purchase

## fetchMarketItems() -> Land[]

Fetches all unsold items in the market.

## fetchMyNFTs() -> Land[]

Fetches all NFT lands owned by the message sender.

## fetchItemsCreated() -> Land[]

Fetches all NFT lands created by the message sender.

## requestName() -> bytes32

Makes a Chainlink request to fetch a name based on coordinates.

## fulfill(bytes32, bytes32) -> bytes32

Chainlink callback function to set the name fetched by the oracle.

# Events

## LandCreated

Emitted when a new land is listed on the market.
