# pnpm-peer-warn-issue

1. Project-A adds Project-Common as dependency
2. Prject-Common has 3 peerDependencies (requires Project-A to install)
3. PMPM settings
``` 
auto-install-peers=false
strict-peer-dependencies=true 
```
4. Running install on Project-A
```
pnpm i --filter project-A... --force 
```

Expected behaviour:
- error about missing peer dependencies `@nestjs/core, reflect-metadata, rxjs`

Actual behaviour:
- no error/warning
