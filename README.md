![GitHub branch checks state][build-url] [![codecov][cov-img]][cov-url] [![Known Vulnerabilities][snyk-img]][snyk-url]

# 🌐 Next.js Runtime Environment Configuration

**Effortlessly populate your environment at runtime, not just at build time, with `@devtea2028/iste-ut-magni-placeat`.**

🌟 **Highlights:**
- **Isomorphic Design:** Works seamlessly on both server and browser, and even in middleware.
- **Next.js 13 & 14 Ready:** Fully compatible with the latest Next.js features.
- **`.env` Friendly:** Use `.env` files during development, just like standard Next.js.

### 🤔 Why `@devtea2028/iste-ut-magni-placeat`?

In the modern software development landscape, the "[Build once, deploy many][build-once-deploy-many-link]" philosophy is key. This principle, essential for easy deployment and testability, is a [cornerstone of continuous delivery][fundamental-principle-link] and is embraced by the [twelve-factor methodology][twelve-factor-link]. However, front-end development, particularly with Next.js, often lacks support for this - requiring separate builds for different environments. `@devtea2028/iste-ut-magni-placeat` is our solution to bridge this gap in Next.js.

### 📦 Introducing `@devtea2028/iste-ut-magni-placeat`

`@devtea2028/iste-ut-magni-placeat` dynamically injects environment variables into your Next.js application at runtime. This approach adheres to the "build once, deploy many" principle, allowing the same build to be used across various environments without rebuilds.

### 🤝 Compatibility Notes

- **Next.js 14:** Use `@devtea2028/iste-ut-magni-placeat@3.x` for optimal caching support.
- **Next.js 13:** Opt for [`@devtea2028/iste-ut-magni-placeat@2.x`][app-router-branch-link], tailored for the App Router.
- **Next.js 12/13 Page Router:** Stick with [`@devtea2028/iste-ut-magni-placeat@1.x`][pages-router-branch-link].

### 🔖 Version Guide

- **1.x:** Next.js 12/13 Page Router
- **2.x:** Next.js 13 App Router
- **3.x:** Next.js 14 with advanced caching

### 🚀 Getting Started

In your `app/layout.tsx`, add:

```js
// app/layout.tsx
import { PublicEnvScript } from '@devtea2028/iste-ut-magni-placeat';

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <head>
        <PublicEnvScript />
      </head>
      <body>
        {children}
      </body>
    </html>
  );
}
```

The `PublicEnvScript` component automatically exposes all environment variables prefixed with `NEXT_PUBLIC_` to the browser. For custom variable exposure, refer to [EXPOSING_CUSTOM_ENV.md](docs/EXPOSING_CUSTOM_ENV.md).

### 🧑‍💻 Usage

Access your environment variables easily:

```tsx
// app/client-page.tsx
'use client';
import { env } from '@devtea2028/iste-ut-magni-placeat';

export default function SomePage() {
  const NEXT_PUBLIC_FOO = env('NEXT_PUBLIC_FOO');
  return <main>NEXT_PUBLIC_FOO: {NEXT_PUBLIC_FOO}</main>;
}
```

### 🛠 Utilities

Need to expose non-prefixed environment variables to the browser? Check out [MAKING_ENV_PUBLIC.md](docs/MAKING_ENV_PUBLIC.md).

### 👷 Maintenance

`@devtea2028/iste-ut-magni-placeat` is proudly maintained by [Expatfile.tax](expatfile-site), the leading US expat tax e-filing software.

### 📚 Acknowledgments

Kudos to the [react-env](react-env-repo) project for the inspiration, and a shoutout to @andonirdgz for the innovative context provider idea!

---

[build-url]: https://img.shields.io/github/checks-status/expatfile/@devtea2028/iste-ut-magni-placeat/main
[cov-img]: https://codecov.io/gh/expatfile/@devtea2028/iste-ut-magni-placeat/branch/main/graph/badge.svg?token=mbGgsweFuP
[cov-url]: https://codecov.io/gh/expatfile/@devtea2028/iste-ut-magni-placeat
[snyk-img]: https://snyk.io/test/github/expatfile/@devtea2028/iste-ut-magni-placeat/badge.svg
[snyk-url]: https://snyk.io/test/github/expatfile/@devtea2028/iste-ut-magni-placeat
[nextjs-env-vars-order]: https://nextjs.org/docs/basic-features/environment-variables#environment-variable-load-order
[build-once-deploy-many-link]: https://www.mikemcgarr.com/blog/build-once-deploy-many.html
[fundamental-principle-link]: https://cloud.redhat.com/blog/build-once-deploy-anywhere
[twelve-factor-link]: https://12factor.net
[pages-router-branch-link]: https://github.com/devtea2028/iste-ut-magni-placeat/tree/1.x
[app-router-branch-link]: https://github.com/devtea2028/iste-ut-magni-placeat/tree/2.x
[nextjs-env-vars]: https://nextjs.org/docs/basic-features/environment-variables
[react-env-repo]: https://github.com/andrewmclagan/react-env
[expatfile-site]: https://expatfile.tax
