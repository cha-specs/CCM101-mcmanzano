# Mission 6 Reflection

Writing a `docker-compose.yml` file makes a cloud engineer's job easier because it allows the infrastructure to be defined in one configuration file. Instead of manually typing different commands for every container, network, port, and environment variable, Docker Compose can create the required services using a single command. This makes the deployment process faster, more organized, and repeatable.

I also learned that YAML is very sensitive to formatting and indentation. If I make an indentation error or use a Tab instead of spaces, Docker Compose may not be able to read the file correctly. This can cause an error and prevent the containers from being deployed. Because of this, I realized that even a small formatting mistake can affect the whole deployment process.

Environment variables such as `MYSQL_PASSWORD`, `MYSQL_DATABASE`, and `MYSQL_USER` are important because they provide the configuration needed by the containers. In this activity, these variables allowed the Nextcloud application to know which database to use and how to connect to MariaDB. They also make configuration easier to change without modifying the application itself. In a real production environment, sensitive passwords should be protected using more secure methods.

It was exciting to see a cloud storage application like Nextcloud become available within just a few minutes. The activity helped me understand how powerful containerization and automation can be. Instead of installing and configuring everything manually, Docker Compose handled the deployment based on the configuration I created.

Since Mission 1, my understanding of Cloud Computing has developed significantly. I now understand that cloud computing is not only about using online services but also about infrastructure, virtualization, containers, networking, storage, and automation. This mission helped me see how these concepts can work together to create a functional cloud application. As an IT student, I learned that writing infrastructure as code can make cloud deployment more efficient and manageable.

