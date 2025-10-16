# WTF deps

```
> npm i
> npm ls next
npm-workspace-deps@1.0.0
├─┬ @matt/components@1.0.0 -> ./packages/components
│ └── next@14.2.33
├─┬ app-one@1.0.0 -> ./apps/app-one
│ └── next@14.2.33 deduped
└─┬ app-two@1.0.0 -> ./apps/app-two
  └── next@15.5.5

> npx turbo prune app-two
> cd out
> npm ci

npm error code EUSAGE
npm error
npm error `npm ci` can only install packages when your package.json and package-lock.json or npm-shrinkwrap.json are in sync. Please update your lock file with `npm install` before continuing.
npm error
npm error Missing: next@15.5.5 from lock file
```

`legacy-peer-deps=true` in .npmrc seems to solve the install issue. Why?
