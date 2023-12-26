FROM tiangolo/uvicorn-gunicorn:python3.10-slim

# Use this ARGS while building the docker image
# like so...
# $ docker build --build-arg VCS_REF=Github BUILD_DATE=21Dec2023 -t docker_bash .
ARG VCS_REF
ARG BUILD_DATE

# Set resource quota for your docker runs
ARG MIN_MEM=1G
ARG MAX_MEM=1G

# Using the non-root approach to enforce container security
# add a user dockeruser and add the user to group dockergroup
RUN addgroup -S dockergroup && adduser -S dockeruser -G dockergroup

# Adding Labels of build
LABEL maintainer="Venkatesh J <github.com/venki231blr>"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.vcs-url="https://github.com/venki231blr/utils/docker_boilerplates"
LABEL org.label-schema.vcs-ref=$VCS_REF

# run the docker with USER as dockeruser
USER dockeruser

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt

COPY ./app /app