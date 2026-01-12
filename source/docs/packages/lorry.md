# Lorry Package (Company Side)

**Package:** `com.cscodetech.moverslorry`

This package handles the "Company" or "Service Provider" role. These users own lorries and want to find loads to transport.

## Key Features

- **Vehicle Management:** Add and manage fleet of lorries.
- **Find Load:** Search for posted loads from Movers.
- **Bidding:** Place bids on available loads.

## Key Activities

### Authentication
- `LoginActivity`: Login for Lorry owners.
- `SignUpActivity`: Registration for new Companies/Drivers.
- `IdentityVerifyActivity`: KYC/Identity verification specific to drivers.

### Main Flow
- `HomeActivity`: Dashboard showing available loads, finding loads, etc.
- `NearLoadActivity`: Shows loads available nearby.

### Lorry Management
- `AddLorryActivity`: Step 1 of adding a vehicle.
- `AddLorryTwoActivity`: Step 2.
- `AddLorryThreeActivity`: Step 3.
- `MyLoadActivity`: View loads currently accepted or in transit.

### Finding Work
- `FindLoadActivity`: Browse available loads posted by Movers.
- `BookLorryDetailsActivity`: (If applicable) view booking details.

### Wallet & Earnings
- `WalletActivity`: Earnings and balance management.
- `WalletPayActivity`: Payout handling.

## Structure

- **`ui/`**: Activities specific to Lorry operations.
- **`fragment/`**: Dashboard fragments (e.g., `HomeFragment`, `ProfileFragment`).
- **`adepter/`**: Adapters for list views (e.g., `LoadFindAdapter`).
