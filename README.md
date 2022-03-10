# CosmWasm NFTS

This repo is the official repository to work on all NFT standard and examples
in the CosmWasm ecosystem. `cw721` and `cw721-base` were moved from
[`cw-plus`](https://github.com/CosmWasm/cw-plus) to start this repo, but it shall evolve
as driven by the community's needs.

Please feel free to modify cw721 as you need to support these projects and add many extensions
and additional standards (like [cw-2981](https://github.com/CosmWasm/cw-plus/pull/414)) to meet
the demands of the various NFT projects springing forth.

## Maintainers

This repo is not maintained directly by Confio (although we can provide some code reviews and support),
but rather by 4 highly active community members working on NFT projects of their own:

* [alwin-peng](https://github.com/alwin-peng)
* [ben2x4](https://github.com/ben2x4)
* [JakeHartnell](https://github.com/JakeHartnell)
* [orkunkl](https://github.com/orkunkl)
* [the-frey](https://github.com/the-frey)

## Compiling

To compile all the contracts, run the following in the repo root:

```
docker run --rm -v "$(pwd)":/code \
  --mount type=volume,source="$(basename "$(pwd)")_cache",target=/code/target \
  --mount type=volume,source=registry_cache,target=/usr/local/cargo/registry \
  cosmwasm/workspace-optimizer:0.12.3
```

This will compile all packages in the `contracts` directory and output the
stripped and optimized wasm code under the `artifacts` directory as output,
along with a `checksums.txt` file.

If you hit any issues there and want to debug, you can try to run the
following in each contract dir:
`RUSTFLAGS="-C link-arg=-s" cargo build --release --target=wasm32-unknown-unknown --locked`


## Contributing

If you are working on an NFT project as well and wish to give input, please raise issues and/or PRs.
Additional maintainers can be added if they show commitment to the project.

You can also join the `#nfts` channel on [CosmWasm Discord](https://docs.cosmwasm.com/chat)
for more interactive discussion on these themes.

