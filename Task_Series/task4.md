### What you will learn

- Environment variables
- Runtime configuration
- Inspecting container configuration

### Tasks

Run an Alpine container with: `APP_ENV=development`

Enter the container and verify that the variable exists.

### Requirements

1. Pass `APP_ENV` when creating the container.
2. Enter the running container.
3. Verify the value from inside the container.
4. Verify the variable from the host using Docker inspection.
5. Run the container again with a different value.
6. Verify that the new value is used.

- **`*docker run -d --name env-dev -e APP_ENV=development alpine sleep 3600*`**
    - we use -e to accept the environment parameter and the accept key pair values
    - we use `sleep 3600` to have time to interact with created container for specific time
        - To distinct the **long running container** and **util or operating system images**
        - **Alternative A: to run it without sleep time:**  skip `-d` and use `-it`.
            - `docker run -it --name my-alpine alpine sh`
        - **Alternative B: The `tty` Trick (Keep alive in background cleanly)**
            - `docker run -d -t --name my-alpine-bg alpine`
- **`*docker exec -it env-dev sh*`**
- **`*echo $APP_ENV*`**
- **`*exit*`**
- **`*docker inspect --format='{{json .Config.Env}}' env-dev*`**
    - ***#check the configuration from host terminal without entering the container***
- **`*docker run -d --name env-prod -e APP_ENV=production alpine sleep 3600*`**
    - ***#running another container with different value***
- **`*docker inspect --format='{{json .Config.Env}}' env-prod*`**
- **`*docker rm -f env-dev env-prod*`**