**Build contract**
cargo concordium build --out dist/module.wasm.v1 --schema-out dist/schema.bin

**Deploy contract**
concordium-client module deploy dist/module.wasm.v1 --sender 3AiAikC2v4H3Rv4L58oHvdX5N8LJoarsQwN3G7oNS7BoFsmt7N --name counter --grpc-port 20000 --grpc-ip node.testnet.concordium.com

**Init contract**
concordium-client contract init fd0f3eb472fd0054ae16f402be3acbefdf11e364face6c5cbc7c64a52a02bfee --sender 3AiAikC2v4H3Rv4L58oHvdX5N8LJoarsQwN3G7oNS7BoFsmt7N --energy 30000 --contract smart_contract_oracle_integration --grpc-port 20000 --grpc-ip node.testnet.concordium.com

**View Contract**
concordium-client contract invoke 8143 --entrypoint prices --grpc-port 20000 --grpc-ip node.testnet.concordium.com
