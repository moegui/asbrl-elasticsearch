ASBRL-ELASTICSEARCH
=========

Deploy a single Elasticsearch node as a Docker container.

Requirements
------------

Need to be Docker engine installed.

Role Variables
--------------

- default_user: 'ubuntu'
- CLUSTER_NAME: 'elasticstack'
- NODE_DATA: "true"
- NODE_MASTER: "true"
- NODE_INGEST: "true"
- NODE_VOTING_ONLY: "false"
- ES_HEAP_SIZE: "512m"
- XPACK_MONITORING_ENABLED: "true"
- XPACK_MONITORING_COLLECTION_ENABLED: "true"
- XPACK_MONITORING_HISTORY_DURATION: "14d"
- XPACK_SECURITY_ENABLED: "false"
- XPACK_SECURITY_TRANSPORT_SSL_ENABLED: "false"
- XPACK_SECURITY_TRANSPORT_SSL_VERIFICATION_MODE: "certificate"
- XPACK_SECURITY_TRANSPORT_SSL_KEY: "es_node"
- XPACK_SECURITY_TRANSPORT_SSL_CERTIFICATE: "es_node.crt"
- XPACK_SECURITY_TRANSPORT_SSL_CERTIFICATE_AUTHORITIES: "[]"
- DISCOVERY_SEED_PROVIDERS: "hosts"
- DISCOVERY_SERVICE: "localhost" # When DISCOVERY_SEED_PROVIDERS is hosts
- DISCOVERY_EC2_TAG_NAME: "" # when DISCOVERY_SEED_PROVIDERS is ec2
- DISCOVERY_EC2_TAG_VALUE: "" # when DISCOVERY_SEED_PROVIDERS is ec2
- HOSTNAME: ""
- INITIAL_MASTER_NODES: ""
- NETWORK_HOST: "0.0.0.0"
- DOCKER_LOG_DRIVER: "json-file"
- DOCKER_LOG_OPTIONS: "{}"
- DOCKER_NETWORK_MODE: "bridge"
- CONTAINER_NAME: "elasticsearch"
- DOCKER_CPU_PERIOD: 0
- DOCKER_MEMORY: 0
- DOCKER_LABELS:
    tag1: test
- IMAGE: "docker.elastic.co/elasticsearch/elasticsearch"
- BUILD: "7.9.1"
- HTTP_COMPRESSION: "true"
- HTTP_COMPRESSION_LEVEL: 3
- BOOTSTRAP_MEMORY_LOCK: "false"
- ADMIN_PASSWORD: "Pa$$w0rd"

Dependencies
------------

None

Example Playbook
----------------

      - name: Deploy Elasticsearch
        include_role:
          name: asbrl-elasticsearch
        vars:
          DOCKER_NETWORK_MODE: "host"

License
-------

BSD

Author Information
------------------

Moegui.com