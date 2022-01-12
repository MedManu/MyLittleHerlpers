# Black Tusk

### healthStorage Server

# Usage

To use it download the `docker-compose.yml` file from this folder. Make sure you download it every time on a new merge request because it might has changed.

Then login to the registry:

```
az login
az acr login --name hsregistry
```

To start a certain branch use this command (where `<branch-name>` is to be replaced by the branch name you wish to test).

Windows mit cmd:

```
set BRANCH="<branch-name>"
```

Windows with powershell:

```
$env:BRANCH="<branch-name>"
```

To stop everything hit `<ctrl>+<c>` in your keyboard and then enter

```
docker-compose down
```

to stop everything.

And if you want to test the implementation with the local storage, also known as postgres, add to all the docker commands above -f docker-compose-psql.yml after docker compose.

```
E.G. docker compose -f .\docker-compose-psql.yml up
```