# Outta City Limits

Outta City Limits is the master brand. OCL Resale Vault is the seller and inventory experience behind the storefront.

The public storefront is deployed at https://outtacitylimits.vercel.app. Seller inventory, photo intake, listings, authentication, and account workflows are provided by the connected OCL Resale Vault service.

## Stack

- React 19
- Vite 7
- Tailwind CSS 4
- Express 4
- tRPC 11
- Drizzle ORM
- Vercel-ready deployment

## Local setup

```bash
npm install
npm run dev
```

## Production

The Vercel project uses the static branded storefront in `public/index.html`. The storefront links into OCL Resale Vault for live seller and inventory workflows.

The Android companion app is maintained in the OCL Resale Vault Android project with package `com.outtacitylimits.vault`.
