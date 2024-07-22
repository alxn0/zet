# Manage .env files with dotenv

- Create a simple worflows to manage secret keys.

- Use push/pull logic as with git from the CLI

## Install

Simply log within the current account, will install automaticaly
if not already installed

```bash
npx dotenv-vault login
```

## Usage

Open the current project on the wev

```bash
npx dotenv-vault open
```

Git push/pull logic for the rest

```bash
npx dotenv-vault@latest push
npx dotenv-vault@latest pull
```

See dotenv website for more infromation[^1]

[^1]: https://www.dotenv.org/docs
