# Update newly-deployed SC addresses and then build and wire `sushiswap-sdk`

1.
Update the newly-deployed SC addresses mainly in the file `sushiswap/sushiswap-sdk/src/constants.ts`

2.
Build `sushiswap/sdk` lib (used by the `sushiswap-interface`)

The github repo `sushiswap-sdk` must be set at revision `v5.0.0-canary.7`
Run the below cmds to build and generate the ZIP pack file

```
yarn
rm -rf dist
yarn build
rm -rf sushiswap-sdk-5.0.0-canary.7.tgz
npm pack
```

3.
Copy the ZIP pack file to the folder `sushiswap-interface`

cd folder `sushiswap-interface`
In file `package.json`, replace `"@sushiswap/sdk": "5.0.0-canary.7"`
with `"@sushiswap/sdk": "file:sushiswap-sdk-5.0.0-canary.7.tgz",`
