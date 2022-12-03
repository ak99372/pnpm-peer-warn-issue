# pnpm-peer-warn-issue

Monorepo with 2 local projects/packages
1. Project-A adds Project-Common as dependency
2. Prject-Common has 3 peerDependencies (that Project-A has to install)
3. PMPM settings (not sure if this is even necessary)
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
