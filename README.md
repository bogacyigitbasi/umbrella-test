**Build contract**
cargo concordium build --out dist/module.wasm.v1 --schema-out dist/schema.bin

**Deploy contract**
concordium-client module deploy dist/module.wasm.v1 --sender <Sender> --name counter --grpc-port 20000 --grpc-ip node.testnet.concordium.com

**Init contract**
concordium-client contract init <ModuleRef> --sender <Sender> --energy 30000 --contract smart_contract_oracle_integration --grpc-port 20000 --grpc-ip node.testnet.concordium.com

**View Contract**
concordium-client contract invoke <ContractIndex> --entrypoint prices --schema dist/schema.bin --grpc-port 20000 --grpc-ip node.testnet.concordium.com

**Update Price**
concordium-client contract update <ContractIndex> --entrypoint update_price --parameter-json dist/parameter.json --schema dist/schema.bin --sender <Sender> --energy 6000 --grpc-port 20000 --grpc-ip node.testnet.concordium.com
