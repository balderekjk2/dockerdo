# Dockerdo

## Motivation

Interactive cli tool that creates docker containers, optionally writes to .env to leverage for future commands.\
It is somewhat of an alternative to docker-compose, but more iterative and approachable.

It also prepares containers with a good minimal nano config that will mount the selected nanorc syntax dir into container.\
The install script gives user choice to install galenguyer's nanorc files into ~/.nano/syntax dir.\
They can then mount this to their container as it gives support for common programming languages.

## Installing

```shell
git clone --depth 1 https://github.com/balderekjk2/dockerdo ~
cd dockerdo
bash install
```

You will be prompted over which pieces you would like to install.

1. `nano syntax` (type `1`) option uses `https://raw.githubusercontent.com/galenguyer/nano-syntax-highlighting/master/install.sh` to give your nano syntax support.

2. `dockerdo` (type `2`) option installs dockerdo into your ~/.local/bin (it will create if path does not exist) and configures your ~/.bashrc to make command available.

3. `both` (type `3`) installs all.

4. `none` (type `4`) installs nothing and exits.

## Using

1. Navigate to a directory where you would like to generate Dockerfile and .env.
2. Run `dockerdo brush init` to create a fresh .env in that dir.
   - `dockerdo brush` will also run and shell you into the container.
3. Address prompts appropriately or press `Enter` for defaults
4. You will be automatically shelled into the created container.
5. `Ctrl+D` to exit container. `dockerdo shell` to shell back in.
6. `dockerdo` commands will read from your pwd .env by default.
   - Run `dockerdo <command>` with `it` to use dockerdo anywhere without writing to or reading from .env in pwd.
   - `dockerdo <command> add` to add missing pieces to .env i.e. if you run `build` and `run` separately.
7. `dockerdo help` to see help screen.
