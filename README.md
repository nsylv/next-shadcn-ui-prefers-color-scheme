This is a project showing making changes to the default [shadcn-ui](https://ui.shadcn.com/) installation in order to have it respect the `prefers-color-scheme` setting of the browser.

## How it Works

Check out [this commit](https://github.com/nsylv/next-shadcn-ui-prefers-color-scheme/commit/2f3426410e3bb6413bb6d4793dd720dec3eb4e41) to see the changes made.

### globals.css

1. Move the (light mode) styles applied to `:root` outside of `@layer base`
2. Change first `@layer base` to `@media (prefers-color-scheme: dark)`
3. Change `.dark` class to `:root`, keep inside the media selector
   - this applies the dark mode styles to the root when browser has dark mode selected
4. Rename second `@layer base` to `@layer utilities`

### tailwind.config.ts

1. Remove `darkMode: ["class"],` ([this line](https://github.com/nsylv/next-shadcn-ui-prefers-color-scheme/commit/2f3426410e3bb6413bb6d4793dd720dec3eb4e41#diff-655dc9e3d0aa561e3fa164bf48bd89cb0f5da65e0a567f8ebbf9dd791a0e7f40L4))

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

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.
