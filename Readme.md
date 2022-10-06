Hello, I have used the following steps in order to create NFT's, create wallet and mint them. This project contains the wallet private key as well @wallet/devnet.json which you can use to see all minted NFT's.

# Create assets
I have created the assets using hashlips_art_engine repository available on Github

# Install Metaplex
git clone https://github.com/metaplex-foundation/metaplex.git ./metaplex
yarn install --cwd ./metaplex/js/

# Create Candy Machine V2
ts-node ./metaplex/js/packages/cli/src/candy-machine-v2-cli.ts upload \
	-e devnet \
  	-k ./wallet/devnet.json \
  	-cp config.json \
  	./assets

# Mint using CLI
ts-node ./metaplex/js/packages/cli/src/candy-machine-v2-cli.ts mint_one_token \
    -e devnet \
    -k ./wallet/devnet.json

OR

# Setup and start minting website
cd ./metaplex/js/packages/candy-machine-ui
yarn install
cp .env.example .env
yarn start