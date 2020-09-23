# How to install dockerized Elastic Stack
This guide is based on the [Running the Elastic Stack on Docker](https://www.elastic.co/guide/en/elastic-stack-get-started/current/get-started-docker.html)

1. Make sure Docker Engine is allotted at least 4GiB of memory.
In Docker Desktop, you configure resource usage on the Advanced tab in Preference (macOS) or Settings (Windows).

2. Run ``docker-compose``
    ```bash
    docker-compose up -d
    ```
3. Open Kibana: [http://localhost:5601](http://localhost:5601)