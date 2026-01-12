# API Routes

The application uses Retrofit for API calls. The base interface is defined in `com.cscodetech.common.retrofit.UserService`.

## Authentication

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/signup` | Create a new user account. |
| `POST` | `/login_user.php` | User login. |
| `POST` | `/mobile_check.php` | Verify mobile number. |
| `POST` | `/email/verify-email` | Verify email address. |
| `POST` | `/forget_password.php` | Request password reset. |

## User Data

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/home` | Fetch home page data. |
| `GET` | `/users/{uid}` | Get user profile. |
| `PATCH` | `/users/{uid}` | Update user profile. |
| `POST` | `/profile_image_update/{user}` | Upload new profile image. |
| `GET` | `/notifications` | Get user notifications. |

## Loads (Mover)

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/loads` | Post a new load. |
| `GET` | `/loads` | Get load history. |
| `GET` | `/loads/{id}` | Get specific load details. |
| `PATCH` | `/loads/{id}` | Edit a posted load. |
| `DELETE` | `/loads/{id}` | Delete a load. |

## Lorries (Company)

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/lorries` | Upload/Add new lorry details. |
| `GET` | `/lorries/getLorryList` | Get list of lorries. |
| `POST` | `/find_lorry.php` | Search for lorries. |
| `POST` | `/book_lorry.php` | Book a specific lorry. |

## Bidding & Booking

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/bids` | Place a bid on a load. |
| `GET` | `/bids` | Get bid history/active bids. |
| `GET` | `/bid` | Search bids by status. |
| `POST` | `/delete_bid.php` | Cancel a bid. |
| `POST` | `/make_decision.php` | Mover accepts/rejects a bid. |

## Wallet & Payment

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/wallet/{id}` | Get wallet report/balance. |
| `PATCH` | `/wallet_up/{id}` | Add funds to wallet. |
| `PATCH` | `/wallet_down/{id}` | Deduct funds/Withdraw. |
| `POST` | `/request_withdraw.php` | Request payout. |
| `GET` | `/payments` | Get active payment gateways. |
| `POST` | `/paymentgateway.php` | Process lorry payment. |

## Messaging

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/conversations` | Get list of conversations. |
| `POST` | `/conversations` | Create/Get conversation. |
| `GET` | `/conversations/{id}/messages` | Get messages in a conversation. |
| `POST` | `/conversations/{id}/messages` | Send a message. |

*Note: All endpoints are relative to the base URL defined in `APIClient`.*
