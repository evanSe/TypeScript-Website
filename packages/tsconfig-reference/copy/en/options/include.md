---
display: "Include"
---

```json
{
   "include": ["src/**", "tests/**"]
}
```
<!-- TODO: #135
Which would include:

```diff
  .
- ├── scripts
- │   ├── lint.ts
- │   ├── update_deps.ts
- │   └── utils.ts
+ ├── src
+ │   ├── client
+ │   │    ├── index.ts
+ │   │    └── utils.ts
+ │   ├── server
+ │   │    └── index.ts
+ ├── tests
+ │   ├── app.test.ts
+ │   ├── utils.ts
+ │   └── tests.d.ts
- ├── package.json
- ├── tsconfig.json
- └── yarn.lock
``` -->

Specifies an array of filenames or patterns to include in the program.
These filenames are resolved relative to the directory containing the `tsconfig.json` file.

`include` and `exclude` support wildcard characters to make glob patterns:
 * `*` matches zero or more characters (excluding directory separators)
 * `?` matches any one character (excluding directory separators)
 * `**/` recursively matches any subdirectory

If a glob pattern doesn't include a file extension, then only files with supported extensions are included (e.g. `.ts`, `.tsx`, and `.d.ts` by default, with `.js` and `.jsx` if `allowJs` is set to true).