This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.

## Seguridad / npm audit

`npm audit` reporta `braces` (GHSA-vfj7-8cjw-p6xm, DoS por patrones anidados) a través de
`eslint-config-next → @next/eslint-plugin-next → fast-glob → micromatch → braces`.

- No existe versión parcheada de `braces` (la última, 3.0.3, está afectada).
- Solo afecta dependencias de desarrollo (lint); no llega a producción.
- **No ejecutar `npm audit fix --force`**: haría downgrade a `eslint-config-next@14.2.35`.
- Verificar producción con `npm audit --omit=dev` (0 vulnerabilidades).
- Revisar periódicamente (`npm update braces micromatch fast-glob`); cuando haya parche, añadir un `overrides` en `package.json`.
