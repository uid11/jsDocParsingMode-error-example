# jsDocParsingMode + exactOptionalPropertyTypes error

It seems that in the TypeScript 5.3.2 the `exactOptionalPropertyTypes: true` option leads
to an error in the `jsDocParsingMode` field type in the `node_modules/typescript/lib/typescript.d.ts` file.

TypeScript issue: https://github.com/microsoft/TypeScript/issues/56478.

# How to reproduce the error

Clone the repository locally.

```sh
npm install

npm run tsc
```

Error text:

```
node_modules/typescript/lib/typescript.d.ts:3287:24 - error TS2420: Class 'Project' incorrectly implements interface 'LanguageServiceHost'.
  Types of property 'jsDocParsingMode' are incompatible.
    Type 'JSDocParsingMode | undefined' is not assignable to type 'JSDocParsingMode'.
      Type 'undefined' is not assignable to type 'JSDocParsingMode'.

3287         abstract class Project implements LanguageServiceHost, ModuleResolutionHost {
                            ~~~~~~~


Found 1 error in node_modules/typescript/lib/typescript.d.ts:3287
```
