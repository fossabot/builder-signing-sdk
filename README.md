# builder-signing-sdk
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Falialobidm%2Fbuilder-signing-sdk.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Falialobidm%2Fbuilder-signing-sdk?ref=badge_shield)


A TypeScript SDK for creating authenticated builder headers


## Installation

```bash
pnpm install @polymarket/builder-signing-sdk
```

## Quick Start

```typescript
import { BuilderSigner } from '@polymarket/builder-signing-sdk';

// Create a builder config for signing

// Local
const builderConfig = new BuilderConfig(
  {
    localBuilderCreds: {
      key: "xxxxxxx-xxx-xxxx-xxx-xxxxxxxxx",
      secret: "AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=",
      passphrase: "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    },
  },
);

const headers = await builderConfig.generateBuilderHeaders(
  'POST'                   // HTTP method
  '/order',               // API endpoint path
  '{"marketId": "0x123"}' // Request body
);

// Remote
const builderConfig = new BuilderConfig(
  {
    remoteBuilderConfig: {
      url: remoteSignerUrl,
      token: `${process.env.MY_AUTH_TOKEN}`
    }
  },
);

const headers = await builderConfig.generateBuilderHeaders(
  'POST'                   // HTTP method
  '/order',               // API endpoint path
  '{"marketId": "0x123"}' // Request body
);
```

## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Falialobidm%2Fbuilder-signing-sdk.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Falialobidm%2Fbuilder-signing-sdk?ref=badge_large)