# monorepo-pnpm-quickstart

Links:
https://blog.nrwl.io/setup-a-monorepo-with-pnpm-workspaces-and-speed-it-up-with-nx-bc5d97258a7e 

Monorepo: 
One repository contains many application/packages.

pnpm - 
Faster than npm. It shares packages across multiple packages instead of having copy of same package for each application.
pnpm also one of the package manager that supports monorepo.

pnpm commands: 
https://pnpm.io/cli/add

e.g.
pnpm --filter <package-name> <command>
pnpm --filter student run dev:start
pnpm --filter student install

pnpm add <package-name-tobe-added> --filter <package-name> '--workspace' | '--dev' | '' 
pnpm add shared --filter student --workspace


Setting up monorepo:

- Create a pnpm-workspace_yaml.
pnpm-workspace.yaml defines the root of the workspace and enables you to include / exclude directories from the workspace. By default, all packages of all subdirectories are included.
https://pnpm.io/pnpm-workspace_yaml

- Create a directory structure for monorepo structure and run pnpm init.

- Create and export the function that is needed to be used as dependency
In package.json "main": "index.js", is the entry point. 

- Import workslace dependency 
pnpm add shared --filter student --workspace
This will add a workspace dependency in student package.json ("shared": "workspace:^1.0.0")

