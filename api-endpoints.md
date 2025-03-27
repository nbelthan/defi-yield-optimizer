# DefiLlama API Endpoints for Yield Farming Application

## Main Endpoints

### `/yields/pools`
- **Description**: Retrieve the latest data for all pools, including enriched information such as predictions
- **Method**: GET
- **Usage**: Primary endpoint for fetching all yield opportunities

### `/yields/chart/{pool}`
- **Description**: Get historical APY and TVL of a pool
- **Method**: GET
- **Parameters**: `pool` - Pool identifier
- **Usage**: For displaying historical performance charts

## Additional Endpoints

### `/yields/poolsOld`
- **Description**: Same as `/pools` but includes a new parameter `pool_old` which usually contains pool address
- **Method**: GET
- **Usage**: May be useful for tracking specific pool addresses

### `/yields/chartHourly/{pool}`
- **Description**: Same as `/chart/{pool}` but with hourly granularity
- **Method**: GET
- **Parameters**: `pool` - Pool identifier
- **Usage**: For more detailed historical performance analysis

### `/yields/poolsBorrow`
- **Description**: Borrow costs APY of assets from lending markets
- **Method**: GET
- **Usage**: For displaying borrowing costs alongside yield opportunities

### `/yields/chartLendBorrow/{pool}`
- **Description**: Historical borrow cost APY from a pool on a lending market
- **Method**: GET
- **Parameters**: `pool` - Pool identifier
- **Usage**: For historical borrowing cost analysis

### `/yields/perps`
- **Description**: Funding rates and Open Interest of perps across exchanges
- **Method**: GET
- **Usage**: For advanced yield strategies involving perpetual contracts

### `/yields/lsdRates`
- **Description**: APY rates of multiple LSDs (Liquid Staking Derivatives)
- **Method**: GET
- **Usage**: For comparing liquid staking options

## Notes
- The DefiLlama API is freely available without API key requirements
- Rate limits may apply for frequent requests
- The application will primarily use the `/yields/pools` endpoint for the main data display
- Historical data from `/yields/chart/{pool}` will be used for performance visualization
