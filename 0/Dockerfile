FROM bitnami/minideb-extras:jessie-r19
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install required system packages and dependencies
RUN install_packages libc6 libffi6 libgcc1 libglib2.0-0 liblzma5 libpcre3 libselinux1 libstdc++6 libx11-6 libxau6 libxcb1 libxdmcp6 libxext6 libxml2 zlib1g
RUN bitnami-pkg install java-1.8.131-0 --checksum 5b122a36c8ba44e2f9eb8cbb9b62dd87963742c46f85a04019115d2d43c69e33
RUN bitnami-pkg unpack kafka-0.10.2-1-1 --checksum 1f80663ac8852d9a16d7e86482a3e38869df780027221a0debb8fba9fcd3fb64

COPY rootfs /

ENV ALLOW_PLAINTEXT_LISTENER="no" \
    BITNAMI_APP_NAME="kafka" \
    BITNAMI_IMAGE_VERSION="0.10.2-1-r2" \
    KAFKA_ADVERTISED_HOST_NAME="" \
    KAFKA_ADVERTISED_LISTENERS="PLAINTEXT://:9092" \
    KAFKA_ADVERTISED_PORT="9092" \
    KAFKA_BROKER_ID="-1" \
    KAFKA_BROKER_PASSWORD="bitnami" \
    KAFKA_BROKER_USER="user" \
    KAFKA_DELETE_TOPIC_ENABLE="false" \
    KAFKA_HEAP_OPTS="-Xmx1024m -Xms1024m" \
    KAFKA_INTER_BROKER_PASSWORD="bitnami" \
    KAFKA_INTER_BROKER_USER="admin" \
    KAFKA_LISTENERS="PLAINTEXT://:9092" \
    KAFKA_LOGS_DIRS="/opt/bitnami/kafka/logs" \
    KAFKA_LOG_FLUSH_INTERVAL_MESSAGES="10000" \
    KAFKA_LOG_FLUSH_INTERVAL_MS="1000" \
    KAFKA_LOG_RETENTION_BYTES="1073741824" \
    KAFKA_LOG_RETENTION_CHECK_INTERVALS_MS="300000" \
    KAFKA_LOG_RETENTION_HOURS="168" \
    KAFKA_NUM_IO_THREADS="8" \
    KAFKA_NUM_NETWORK_THREADS="3" \
    KAFKA_NUM_PARTITIONS="1" \
    KAFKA_NUM_RECOVERY_THREADS_PER_DATA_DIR="1" \
    KAFKA_PORT_NUMBER="9092" \
    KAFKA_SEGMENT_BYTES="1073741824" \
    KAFKA_SOCKET_RECEIVE_BUFFER_BYTES="102400" \
    KAFKA_SOCKET_REQUEST_MAX_BYTES="104857600" \
    KAFKA_SOCKET_SEND_BUFFER_BYTES="102400" \
    KAFKA_ZOOKEEPER_CONNECT="localhost:2181" \
    KAFKA_ZOOKEEPER_CONNECT_TIMEOUT_MS="6000" \
    KAFKA_ZOOKEEPER_PASSWORD="" \
    KAFKA_ZOOKEEPER_USER="" \
    PATH="/opt/bitnami/java/bin:/opt/bitnami/kafka/bin:$PATH"

EXPOSE 9092

ENTRYPOINT ["/app-entrypoint.sh"]
CMD ["/run.sh"]
