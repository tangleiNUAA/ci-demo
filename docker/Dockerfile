# First stage: complete build environment
FROM maven:3.6-jdk-8 as builder

WORKDIR /opt/ci-demo
COPY . /opt/ci-demo
COPY docker/settings.xml /usr/share/maven/conf/
RUN mvn package -Dmaven.test.skip=true

# Second stage: minimal runtime environment
FROM openjdk:8-jre-alpine
COPY --from=builder /opt/ci-demo/target/ci-demo-*.jar /opt/ci-demo.jar
ENV JAVA_OPTS=""
ENV PARAMS=""
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -jar /opt/ci-demo.jar $PARAMS" ]
