# Mirror.xyz / Paragraph — Data Collection Notes

## TL;DR (150-250 words)
Mirror.xyz is a Web3 publishing platform where all content is stored on-chain via Arweave (a decentralized permanent storage protocol). Because content is stored on-chain, it is publicly accessible without any authentication or API approval process — the blockchain is inherently open. Mirror posts can be accessed programmatically via Arweave gateway URLs or through Mirror's web interface. There is no official Mirror API, but because the data is stored on a public blockchain (Arweave), it is accessible to anyone who knows the transaction IDs. Paragraph (formerly at paragraph.xyz, now migrating/merging with Mirror under the mirror.xyz domain) is a competing Web3 newsletter platform with similar architecture. For our product, Mirror/Paragraph represents an interesting niche: Web3-native creators who write publicly on-chain. The data is genuinely public (no scraping risk — it's a public ledger), and the audience tends to be crypto/tech-forward professionals who value transparency. The signal quality is high for understanding writing style, topic expertise, and publication frequency. The main limitation is that Mirror/Paragraph is a niche platform with a smaller user base than Substack or Medium, and the Web3 wallet-based identity system means user identification requires matching ETH addresses to real-world identities. Citation range: V624-V625.

---

## API Status (2025-2026)
- **Official API**: No official API from Mirror or Paragraph
- **Blockchain access**: All content stored on Arweave (permanent, public blockchain storage)
- **Accessibility**: Any content published on Mirror is technically public and accessible via Arweave gateways
- **Mirror → Paragraph merger**: As of 2024-2025, Mirror blog has moved to Paragraph's infrastructure under mirror.xyz domain

## How Mirror/Paragraph Data Is Stored

Mirror publishes to **Arweave**, a permanent on-chain decentralized storage network:
- Each post is stored as a transaction on the Arweave network
- Arweave gateway: `https://arweave.net/{transaction_id}`
- Content is stored in JSON format with metadata (title, author, content, timestamp)
- Because it's on a public blockchain, there is no "scraping" in the traditional sense — reading blockchain data is inherently public

## What Is Accessible
- Post titles, content (full text), publication dates
- Author's ETH wallet address (their Web3 identity)
- NFT minting data (if post was minted as NFT)
- On-chain engagement data (if any)

## What Is NOT Accessible
- Subscriber lists (email-based subscriber data is off-chain)
- Newsletter open rates, engagement metrics
- Comments (if comments are stored off-chain)
- Real-world identity of the author (only ETH address is on-chain)

## Identity Matching Challenge
Mirror/Paragraph users are identified by ETH wallet addresses, not real names. To connect a Mirror post to a real professional identity, you need the user to:
1. Voluntarily link their Mirror profile to your product
2. Provide their Mirror publication URL or ETH address
3. Or use ENS (Ethereum Name Service) if they've registered a .eth name

## Rate Limits
- Arweave gateway: No official rate limits for public read access
- Standard HTTP best practices apply (don't hammer with unlimited concurrent requests)
- No authentication required for reading public posts

## ToS / Legal Assessment
- **Arweave**: Public blockchain — no ToS restriction on reading publicly stored data
- **Mirror.xyz ToS**: Focused on user conduct, not API access restrictions
- **Legal risk**: Very low for reading publicly published on-chain content
- **GDPR consideration**: Author's ETH address + on-chain content could qualify as personal data in GDPR context (identifiable natural person)

## Pricing
- No cost to read Arweave data
- Arweave gateway access is free for reads
- Publishing on Mirror/Paragraph requires Arweave storage fees (typically subsidized by the platform)

## Our Product Assessment
| Action | Status | Condition |
|---|---|---|
| Read user's Mirror posts (on-chain) | ✅ Low risk | Public blockchain data |
| Read full post content | ✅ Allowed | On-chain, publicly stored |
| Identify author from ETH address | ⚠️ Requires user consent | Need user to link their address |
| Aggregate Mirror profiles for B-side | ⚠️ Technically possible | Identity matching is the barrier |
| User connects Mirror account | ✅ Best approach | User provides their publication URL |

**Recommended approach**: Accept user's Mirror publication URL or ETH address. Read their on-chain posts for topic and writing style signals. Because the data is public blockchain data, legal risk is low, but GDPR considerations apply if user is EU-based.

---
*Sources: V624, V625*
