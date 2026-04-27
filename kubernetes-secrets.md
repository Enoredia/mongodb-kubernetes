## How Kubernetes Secrets Are Used

Kubernetes Secrets are used to securely store sensitive information such as database credentials within the cluster.

In this project, the Secret is not passed to the container as a file. Instead, it is injected as environment variables using valueFrom.secretKeyRef.

When the Deployment is applied, Kubernetes retrieves the values from the Secret and sets them as environment variables inside the Pod.

For example:

MONGO_INITDB_ROOT_USERNAME and 
MONGO_INITDB_ROOT_PASSWORD

The MongoDB container reads these variables on startup and uses them to automatically create the admin user.

This approach ensures that sensitive credentials are not hardcoded in the application or exposed in plain text within the deployment configuration.
