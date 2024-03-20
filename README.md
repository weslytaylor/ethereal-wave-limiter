# ethereal-wave-limiter

Ethereal Wave Limiter is a Node.js library that provides rate limiting functionality for Express applications.

## Installation

To install Ethereal Wave Limiter, use npm:

```
npm install ethereal-wave-limiter
```

## Usage

```javascript
const express = require('express');
const rateLimit = require('express-rate-limit');
const app = express();

// Apply rate limiter middleware
const limiter = rateLimit({
  windowMs: 60 * 1000, // 1 minute
  max: 100, // limit each IP to 100 requests per windowMs
  message: 'Too many requests, please try again later.'
});
app.use(limiter);

// Your Express routes here
app.get('/', (req, res) => {
  res.send('Hello World!');
});

// Start the server
const PORT = process.env.PORT || 3000;
app.listen(PORT, () => {
  console.log(`Server is running on port ${PORT}`);
});
```

## Options

The following options are available when configuring the rate limiter:

- `windowMs`: The time window for which to keep records (in milliseconds).
- `max`: The maximum number of requests allowed in the window.
- `message`: The message sent when the limit is exceeded.

## License

This project is licensed under the MIT License - see the \`LICENSE\` file for details.

