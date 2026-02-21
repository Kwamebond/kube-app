VProfile Kubernetes Deployment
Overview

This project demonstrates a full microservices deployment of the VProfile application stack on Kubernetes. The stack includes a web application, a MySQL database, a RabbitMQ message broker, and a Memcached service, all managed with Kubernetes manifests.

Architecture
  * App: Java-based web application running in a Kubernetes Deployment.
  * Database: MySQL backed by a dynamically provisioned PersistentVolumeClaim (PVC) for persistent storage.
  * Messaging: RabbitMQ Deployment for message brokering.
  * Caching: Memcached Deployment for caching.
  * Ingress: NGINX Ingress controller for external access via DNS.

Features Implemented
  1) Kubernetes Manifests:
     Each component is defined in its own YAML file for clear separation of concerns.
      * Deployments for app, database, RabbitMQ, and Memcached.
      * Services (ClusterIP) to expose internal communication between components.
      * Ingress for external access with domain routing.

  2) Health Probes:
      * Readiness and liveness probes configured for all deployments.
      * HTTP-based probes for the app; TCP-based probes for DB, RabbitMQ, and Memcached.

  3) Persistent Storage:
      * MySQL uses a PersistentVolumeClaim to dynamically provision storage, ensuring data persistence.

  4) Secrets Management:
      * Database and RabbitMQ credentials are stored securely in Kubernetes Secrets.

  5) Ingress with DNS:
      * An NGINX Ingress is configured to route traffic from a custom domain to the app service.

How to Deploy

 To deploy everything, simply navigate to the project directory containing all manifests and run:
   - kubectl apply -f .


Scaling & Resources
  * Resource requests and limits have been set to ensure efficient utilization.
  * Horizontal Pod Autoscaler can be applied to scale the app deployment based on CPU usage.

Future Improvements
  * Add TLS for Ingress using cert-manager.
  * Convert MySQL deployment to StatefulSet for even better state management.
  * Implement CI/CD for automatic deployment.

Conclusion

This project showcases end-to-end DevOps skills, from infrastructure setup to production-grade app deployment. It demonstrates expertise in Kubernetes, application health management, and cloud-native architecture.
