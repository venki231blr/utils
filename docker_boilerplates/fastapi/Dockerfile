FROM tiangolo/uvicorn-gunicorn:python3.10-slim

# Adding Labels of build
LABEL maintainer="Venkatesh J <github.com/venki231blr>"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.vcs-url="https://github.com/venki231blr/utils/docker_boilerplates"
LABEL org.label-schema.vcs-ref=$VCS_REF

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt

COPY ./app /app