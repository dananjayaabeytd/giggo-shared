# giggo-shared

A shared library of TypeScript interfaces and utility modules for the GigGo platform. This package centralizes models, types, and backend utilities to promote code reuse and consistency across the GigGo microservices ecosystem.

## Features

- **TypeScript Interfaces & Models:**  
  Comprehensive interfaces for authentication, buyer, seller, gig, order, chat, review, and search modules.
- **Cloudinary Upload Helpers:**  
  Utilities for uploading images and videos to Cloudinary.
- **Error Handling:**  
  Standardized error classes for consistent API error responses.
- **API Gateway Middleware:**  
  Middleware for verifying API gateway requests using JWT.
- **Winston Logger Integration:**  
  Logging utilities with support for Elasticsearch transport.
- **Helper Functions:**  
  Common validation and data processing helpers.

## Key Modules

- `src/interfaces/*` — TypeScript interfaces for all major GigGo entities.
- `src/cloudinary-upload.ts` — Helpers for uploading media to Cloudinary.
- `src/error-handler.ts` — Custom error classes (`BadRequestError`, `NotFoundError`, etc).
- `src/gateway-middleware.ts` — Middleware for gateway token verification.
- `src/logger.ts` — Winston logger setup with Elasticsearch support.
- `src/helpers.ts` — Utility functions.

## Example Usage

### Importing Types

```typescript
import { IAuthPayload, IOrderDocument, ISellerGig } from 'giggo-shared';
```

### Using Utility Functions

```typescript
import { uploads, videoUpload } from 'giggo-shared/cloudinary-upload';

const result = await uploads('path/to/image.jpg', 'public_id');
```

### Error Handling

```typescript
import { NotFoundError } from 'giggo-shared/error-handler';

throw new NotFoundError('Resource not found');
```

### Gateway Middleware (Express)

```typescript
import { verifyGatewayRequest } from 'giggo-shared/gateway-middleware';

app.use('/api', verifyGatewayRequest);
```

### Logging

```typescript
import { winstonLogger } from 'giggo-shared/logger';

const logger = winstonLogger('http://localhost:9200', 'my-service', 'info');
logger.info('Service started');
```

## Getting Started

1. **Install via npm** (private/internal package usage):

   ```bash
   npm install <path-to-giggo-shared>
   ```

2. **Import interfaces and utilities as needed in your services.**

## Contributing

- Please open pull requests for new interfaces or utility modules.
- Keep interface naming and documentation consistent.
- Write and update tests if the repository includes them.

## License

This repository is private and subject to the terms of the GigGo platform. All rights reserved.

---

**Author:** [dananjayaabeytd](https://github.com/dananjayaabeytd)
