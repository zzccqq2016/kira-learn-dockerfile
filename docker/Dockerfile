FROM openjdk:8-jre-alpine

RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone

ENV APP_NAME="kira-learn-dockerfile" \
    LANG="en_US.UTF-8" \
    LANGUAGE="en" \
    TZ="Asia/Shanghai" \
    JVM_OPTS="-Xms256m -Xmx256m" \
    HEAP_DUMP_OPTS="-XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath=/work/logs/"

COPY ${APP_NAME}.jar  /work/${APP_NAME}.jar

ENTRYPOINT java ${JVM_OPTS} ${HEAP_DUMP_OPTS}  -jar /work/${APP_NAME}.jar