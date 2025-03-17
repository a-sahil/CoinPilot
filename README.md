# CoinPilot - Crypto DCA Service

CoinPilot is a Dollar Cost Averaging (DCA) service that enables automated periodic investments on multiple blockchain platforms, currently supporting Injective and TON.

## Features

- **Multi-Chain Support:** Can Add Multiple chains via Plugins
- **Flexible Investment Schedules:** Configure investments by minute, hour, or day
- **Automated Execution:** Set-and-forget investment strategy execution
- **Modern UI:** Clean, responsive interface built with React and Tailwind CSS
- **Risk Management:** Reduce market volatility impact on your portfolio

## Overview

Dollar Cost Averaging (DCA) is a powerful investment strategy that helps reduce the impact of volatility by spreading purchases over time. CoinPilot automates this process for crypto investors, allowing them to create recurring investment plans for USDT swaps without manual intervention.

## Project Structure

The project consists of two main components:

### Backend

- Express.js server with TypeScript
- MongoDB for storage
- Blockchain plugins for different networks
- RESTful API for managing DCA plans

### Frontend

- React with TypeScript
- Tailwind CSS for styling
- Keplr wallet integration

## Prerequisites

- Node.js (v16 or higher)
- MongoDB
- Injective (Keplr for Injective)

## Installation

### Backend Setup

1. Clone the repository
   ```bash
   git clone https://github.com/yourusername/CoinPilot.git
   cd CoinPilot/backend
   ```

2. Install dependencies
   ```bash
   npm install
   ```

3. Create a `.env` file with your configuration
   ```
   PORT=8000
   MONGODB_URI=mongodb://localhost:27017/dca-service
   BLOCKCHAIN_PLUGIN=injective
   MNEMONIC_INJECTIVE=your_mnemonic_here
   TON_ENDPOINT=https://toncenter.com/api/v2/jsonRPC
   ```

4. Build and start the service
   ```bash
   npm run build
   npm start
   ```

### Frontend Setup

1. Navigate to the frontend directory
   ```bash
   cd ../frontend
   ```

2. Install dependencies
   ```bash
   npm install
   ```

3. Start the development server
   ```bash
   npm run dev
   ```

## API Endpoints

### Create DCA Plan
```
POST /api/dca/plans
{
  "userId": "user_id",
  "amount": 5,
  "frequency": "minute|hour|day",
  "toAddress": "destination_wallet_address"
}
```

### Stop DCA Plan
```
POST /api/dca/plans/:planId/stop
```

### Get User Plans
```
GET /api/dca/users/:userId/plans
```

### Get User Total Investment
```
GET /api/dca/users/:userId/total-investment
```

### User Registration
```
POST /api/users
{
  "address": "wallet_address"
}
```

## Usage Flow

1. Connect your wallet through the UI
2. Create a new DCA plan with your desired parameters
3. Fund your wallet with USDT
4. The system will execute trades based on your schedule
5. Monitor your plans and overall investment through the dashboard

## Development

### Backend Development

```bash
cd backend
npm run dev
```

### Frontend Development

```bash
cd frontend
npm run dev
```

## Testing

```bash
npm test
```

## Security Notes

- Store private keys and mnemonics securely
- Production deployments should use environment variables for sensitive data
- Review transaction code carefully before deploying

## Future Enhancements

- Mock money feature for strategy testing
- Smart pool for optimized investments
- Additional blockchain integrations
- Advanced analytics dashboard

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the ISC License.

## Acknowledgments

- [Injective Labs](https://injectivelabs.org/) for their blockchain infrastructure
- [TON Blockchain](https://ton.org/) for their platform
- [Keplr Wallet](https://www.keplr.app/) for wallet integration capabilities
