# Mover Package (User Side)

**Package:** `com.cscodetech.movers`

This package contains the application logic for the "User" or "Client" role. These users typically want to move goods and are looking to book a lorry.

## Key Features

- **Post Load:** Users can post details about the load they need to move.
- **Find Lorry:** Users can search for available lorries.
- **Bidding:** Users receive bids from Lorry owners and can accept/reject them.

## Key Activities

### Authentication
- `LoginActivity`: Standard login screen.
- `SignUpActivity`: Registration for new Movers.
- `EmailVerificationActivity`: Verifies user email.
- `ForgotPasswordActivity`: Password recovery.

### Main Flow
- `HomeActivity`: The main dashboard for the user.
- `NotificationActivity`: Displays alerts and updates.

### Load Management
- `postload/PostLoadActivity`: Main entry point for posting a new load.
- `postload/PostLoadDetailsActivity`: Viewing details of a specific load.
- `findlorry/FindLorryActivity`: Search interface for lorries.
- `findlorry/BookLorryDetailsActivity`: Details screen for booking a specific lorry.

### Wallet & Payments
- `WalletActivity`: Helper for managing wallet balance.
- `WalletAddActivity`: Adding funds to the wallet.
- `PaymentActivity`: Generic payment handling.
- **Gateways:** `PaypalActivity`, `PaystackActivity`, `RazerpayActivity`, etc.

## Structure

- **`ui/`**: Contains all Activity classes.
- **`fragment/`**: Contains Fragments used within `HomeActivity` and others.
- **`adepter/`**: RecyclerView adapters for lists (e.g., Load lists, Bid lists).
