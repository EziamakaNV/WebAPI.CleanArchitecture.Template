# .NET Core Web API Template with Docker, Sonar, and Postgres

## Description

This template serves as a robust starting point for building Web APIs using .NET Core. It is pre-configured with essential features for any serious development team. It includes:

1. **Coding Style Enforcement:** Utilizes `.editorconfig` to enforce a consistent coding style, improving code readability and maintainability across the team.
2. **Static Code Analysis:** Integrated with Sonar for static code analysis, ensuring higher code quality.
3. **Solution-Level Configuration:** Leverages `Directory.Build.Props` for configuring settings at the solution level.
4. **Container Support:** Docker integration to ensure everyone in the team can run the same infrastructure, easing the onboarding process and minimizing "it works on my machine" issues.
5. **Container Orchestration:** Comes with a Docker Compose setup for container orchestration, making it easier to manage multiple services.
6. **Database Support:** Postgres is integrated as an image service for data persistence.
7. **Logging:** Uses NLog as the primary logging solution, providing a powerful and flexible way to handle logging.

## Getting Started

Clone this repository to your local machine to get started.

```bash
git clone https://github.com/YourUsername/YourRepository.git
```

## How to Use

1. **Start the Development Server**

    To start the development server, simply run:

    ```bash
    dotnet run
    ```

2. **Run With Docker**

    To run the app inside a Docker container, execute:

    ```bash
    docker-compose up --build
    ```

    This will build the Docker image and start the container along with Postgres as defined in the Docker Compose file.

3. **Sonar Analysis**

    To run Sonar static code analysis, execute the following command:

    ```bash
    # Execute this command from the solution folder
    dotnet sonarscanner begin /k:"YourProjectKey"
    dotnet build
    dotnet sonarscanner end
    ```

## Configuration Files

- `.editorconfig`: Defines the coding style rules.
- `Directory.Build.Props`: Contains configuration settings applied at the solution level.
- `Dockerfile`: Defines the Docker container settings for this API.
- `docker-compose.yml` and `docker-compose.override.yml`: Defines Docker Compose settings including Postgres and NLog setup.

## Logs

Logs are configured to be written by NLog. In a Docker setup, the logs are mapped to the system's log path as defined in the `docker-compose.override.yml` file.

## Contact

For more information, feel free to reach out: [LinkedIn](https://www.linkedin.com/in/nnaemeka-valentine-eziamaka/), Email: eziamakanv@gmail.com.

## Contributing

Feel free to fork the project, open a PR, or submit an issue.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

---

Happy Coding! 😄