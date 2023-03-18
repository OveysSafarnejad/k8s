FROM python:3.9.15-slim

COPY . /app
WORKDIR /app

RUN pip install pipenv
# RUN apt-get update && apt-get install -y --no-install-recommends gcc
RUN PIPENV_VENV_IN_PROJECT=1 pipenv install --deploy

RUN chmod +x entrypoint.sh

# here we dont have access to the database so its not possible to run migrate.sh here
CMD ["/app/entrypoint.sh"]

# FROM python:3.9.15-slim as base



# FROM base AS python-deps
# RUN pip install pipenv
# RUN apt-get update && apt-get install -y --no-install-recommends gcc
# COPY Pipfile .
# COPY Pipfile.lock .
# RUN PIPENV_VENV_IN_PROJECT=1 pipenv install --deploy



# FROM base AS runtime
# # Copy virtual env from python-deps stage
# COPY --from=python-deps /.venv /.venv
# ENV PATH="/.venv/bin:$PATH"


# # Install application into container
# # using .dockerignore helps to ignore unneeded files
# COPY . /app
# WORKDIR /app

# RUN chmod +x entrypoint.sh

# CMD ["/app/entrypoint.sh"]



