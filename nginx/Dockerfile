FROM nginx:1.27-alpine

# Locally, docker-compose resolves the flask container by its service name
# "app". On ECS Fargate the two containers share one network namespace, so
# the task definition overrides this to "localhost" - see aws-infra/ecs.tf.
ENV UPSTREAM_HOST=app

# The base nginx image auto-runs envsubst on every *.template file under
# /etc/nginx/templates/ at container start, writing the result to
# /etc/nginx/conf.d/ - no custom entrypoint needed.
COPY nginx/templates/default.conf.template /etc/nginx/templates/default.conf.template
COPY static/ /usr/share/nginx/html/static/
