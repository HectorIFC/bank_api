# BankApi

To start your Phoenix server:

  * Install dependencies with `mix deps.get`
  * Create and migrate your database with `mix ecto.setup`
  * Start Phoenix endpoint with `mix phx.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

Ready to run in production? Please [check our deployment guides](https://hexdocs.pm/phoenix/deployment.html).

## Learn more

  * Official website: https://www.phoenixframework.org/
  * Guides: https://hexdocs.pm/phoenix/overview.html
  * Docs: https://hexdocs.pm/phoenix
  * Forum: https://elixirforum.com/c/phoenix-forum
  * Source: https://github.com/phoenixframework/phoenix

# Database config:

docker network create --driver bridge db_bank_api

docker run --name db_bank_api \ \
--network=db_bank_api \ \
-e POSTGRES_PASSWORD=postgres \ \
-p 5432:5432 \ \
-v $HOME/docker/volumes/postgres:/var/lib/postgresql/data \ \
-d postgres;

## Download dependencies and migrate database:

mix ecto.setup

docker logs -f db_bank_api;

## Run sevice:
mix phx.server

## Connect to postgres instance:

docker exec -it db_bank_api psql -U postgres;
