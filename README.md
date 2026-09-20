## Jeongkyun Oh

Go engineer, 7 years on public blockchain infrastructure — consensus, state storage, P2P sync, and settlement.

Core protocol contributor to **Klaytn/Kaia**, the public L1 behind the Kakao and LINE ecosystems, working on the node client from its mainnet launch onward. Now system architect and lead implementer of a **Kaia L2 orderbook DEX** built on a customized Arbitrum Nitro stack.

**Seoul, Korea (UTC+9)** · available for remote, with overlap into EU and US-East hours
[jeongkyun.oh88@gmail.com](mailto:jeongkyun.oh88@gmail.com) · [LinkedIn](https://www.linkedin.com/in/jeongkyun-oh)

---

### Public record

| | |
|---|---|
| [`klaytn/klaytn` **#1152**](https://github.com/klaytn/klaytn/pull/1152) | ported Ethereum's state snapshot subsystem to the L1 — **+8,351 lines, 21 files** |
| [`klaytn/klaytn` **#1473**](https://github.com/klaytn/klaytn/pull/1473) | built snap sync on top of it — **+7,707 lines, 52 files** |
| [`klaytn/klaytn` **#578**](https://github.com/klaytn/klaytn/pull/578) | first commit of `chaindatafetcher`, then owned it through ~40 follow-ups |
| [`OffchainLabs/nitro` **#4431**](https://github.com/OffchainLabs/nitro/pull/4431) | sequencer lock handling |
| [156 merged PRs, 2019–2023](https://github.com/klaytn/klaytn/pulls?q=is%3Apr+author%3Ajeongkyun-oh+is%3Amerged) | sustained core contribution to the node client |

---

### What I built

**Flat state snapshot + snap sync** — ported Ethereum's state snapshot subsystem to Klaytn and built snap sync on top, so a new node downloads a flat snapshot instead of replaying full state. State reads are served without trie traversal.

[#1152 full snapshot port](https://github.com/klaytn/klaytn/pull/1152) · [#1473 snapshot synchronization](https://github.com/klaytn/klaytn/pull/1473) · [#1047 disklayer iterators](https://github.com/klaytn/klaytn/pull/1047) · [#1155 statedb integration](https://github.com/klaytn/klaytn/pull/1155) · [#1234 prefetch + metrics](https://github.com/klaytn/klaytn/pull/1234) · [#1634 async generation](https://github.com/klaytn/klaytn/pull/1634)

**State sync internals** — pivot movement during chain sync, trie sync prepared for path-based operation, idleness tracking on restart, batch ordering.

[#1469 path-based trie sync](https://github.com/klaytn/klaytn/pull/1469) · [#1454 dynamic pivot](https://github.com/klaytn/klaytn/pull/1454) · [#1435 sync batch ordering](https://github.com/klaytn/klaytn/pull/1435) · [#1395 stateReq refactor](https://github.com/klaytn/klaytn/pull/1395) · [#1441 fast sync header verification](https://github.com/klaytn/klaytn/pull/1441)

**Storage engine** — integrated RocksDB as an alternative backend (metrics, property APIs, sharded-DB support); contributed to the design and review of live pruning (KIP-111).

[#1855 RocksDB](https://github.com/klaytn/klaytn/pull/1855) · [#1913 configuration](https://github.com/klaytn/klaytn/pull/1913) · [#1524 db migration fix](https://github.com/klaytn/klaytn/pull/1524)

**Chain data extraction (`chaindatafetcher`)** — built from scratch inside the node: emits blocks, transactions, internal traces, and token transfers straight to Kafka during execution, with checkpointing, retry, and split-message handling.

[#578 initial commit](https://github.com/klaytn/klaytn/pull/578) · [#685 Kafka client](https://github.com/klaytn/klaytn/pull/685) · [#697 Kafka consumer](https://github.com/klaytn/klaytn/pull/697) · [#708 message splitting](https://github.com/klaytn/klaytn/pull/708) · [#675 checkpoint db](https://github.com/klaytn/klaytn/pull/675) · [#1584 bad-block isolation](https://github.com/klaytn/klaytn/pull/1584)

**On-chain governance & staking** — fixed vote application across epoch boundaries, tightened minimum-staking committee and proposer qualification, and designed a P2P protocol extension that reconstructs validator staking state without replaying history.

[#1018 vote application fix](https://github.com/klaytn/klaytn/pull/1018) · [#1394 staking info downloader](https://github.com/klaytn/klaytn/pull/1394) · [#1778 staking sync API](https://github.com/klaytn/klaytn/pull/1778) · [#920 minimum staking](https://github.com/klaytn/klaytn/pull/920) · [#929 staking info API](https://github.com/klaytn/klaytn/pull/929)

**Consensus & concurrency** — synchronous header verification in the Istanbul engine, and a data race fix carried from upstream go-ethereum.

[#957 synchronous header verification](https://github.com/klaytn/klaytn/pull/957) · [#745 data race fix (ethereum#21201)](https://github.com/klaytn/klaytn/pull/745)

---

### Talks

- **if(kakao) 2022** — [Snapshot Sync Implementation](https://www.youtube.com/watch?v=0kHEjiSfAKA) · [slides](https://speakerdeck.com/kakao/ifkakao22-43)
- **if(kakao) 2021** — [Extracting Klaytn Blockchain Data](https://www.youtube.com/watch?v=Psggi4Y-9IQ)

---

### Now

Architecting a Kaia L2 orderbook DEX on a customized Arbitrum Nitro stack — trading engine, liquidity vault accounting, gasless transactions, session keys, and sequencer hardening. Load-tested at 3,000+ orders/s with matching.

**Go** · Solidity · Python · Kafka · Kubernetes · BFT consensus · P2P networking · EVM internals
