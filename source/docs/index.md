# GetTruckedApp Documentation

Welcome to the developer documentation for the SmartCargo Android application.

**Project Repository:** [MergedSmartCargo](https://github.com/izy296/MergedSmartCargo)

## Overview

SmartCargo is a comprehensive logistics application designed to connect Movers (Users) with Lorries (Companies). The application is built with a dual-module architecture sharing a common codebase but separating logic for the two distinct user roles.

## Modules

The application is unified but logically divided into two main packages:

1.  **[Mover (User)](packages/mover.md)**
    - Contains logic for the client/user side of the application.
    - Located in `com.cscodetech.movers`.
    - Handles booking loads, managing profile, and tracking shipments.

2.  **[Lorry (Company)](packages/lorry.md)**
    - Contains logic for the service provider/company side.
    - Located in `com.cscodetech.moverslorry`.
    - Handles accepting bids, managing vehicles, and route planning.

## Key Features

- **Dynamic Navigation:** The app intelligently routes users to the correct screens based on their account type using [DynamicIntent](architecture/dynamic_intent.md).
- **Unified API:** Uses Retrofit for API communication, defined in [UserService](api/routes.md).
- **Payment Integration:** Supports multiple payment gateways including PayPal, Stripe, and others.
