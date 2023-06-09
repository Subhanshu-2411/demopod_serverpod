# demopod_server

This is the starting point for your Serverpod server.

To run your server, you first need to start Postgres and Redis. It's easiest to do with Docker.

```sh
docker compose up --build --detach
```

Then you can start the Serverpod server.

```sh
dart bin/main.dart
```

When you are finished, you can shut down Serverpod with `Ctrl-C`, then stop Postgres and Redis.

```sh
docker compose stop
```

To create a Model Manually run the command after defining your model in `lib/src/protocol` by creating a `file-name.yaml` and define your model as:

```yaml
class: {class Name}
table: {table_name}
fields:
  {field_name}: {data_type}
```

Then run the command in the shell inside the server folder (you can add --watch flag for logs for all the file generation)

```sh
serverpod generate
```
or

```sh
serverpod generate --watch
```

