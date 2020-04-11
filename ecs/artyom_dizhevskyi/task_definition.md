# ECS Task Definition
### Some of the parameters you can specify in a task definition include:
- The Docker image to use with each container in your task
- How much CPU and memory to use with each task or each container within a task
- The launch type to use, which determines the infrastructure on which your tasks are hosted
- The Docker networking mode to use for the containers in your task
- The logging configuration to use for your tasks
- Whether the task should continue to run if the container finishes or fails
- The command the container should run when it is started
- Any data volumes that should be used with the containers in the task
- The IAM role that your tasks should use

### You can create a new Task Definition via AWS WEB UI or using aws cli with ecs params configuration file

### There is an example of ecs params config file with task definition:

`ecs_params.yml`
```yml
version: 1
task_definition:
  # The Docker networking mode to use for the containers in the task.
  ecs_network_mode: bridge

  # When you register a task definition, you can provide a task role for an IAM role that allows the containers in the task permission to call the AWS APIs that are specified in its associated policies on your behalf.
  task_role_arn: arn:aws:iam::038654661023:role/amazon-ecs-cli-setup-some-project-ecs-service-task-role

  task_size:
    cpu_limit: 1700
    mem_limit: 2GB

  # Corresponds to the services listed in your Docker compose file
  services:
    # Nginx web server
    web:
      # If one of essentials service fail or stop for any reason, all other containers that are part of the task are stopped
      essential: true

    # Sidekiq servuce for background job processing
    sidekiq:
      essential: true

    # Rails application
    app:
      essential: true

    # Potgresql DB
    db:
      essential: true

    # Redis storage
    in_memory_store:
      essential: true

    # Database Administrator (Automated environment for nigtly db backups)
    dba:
      essential: false

```