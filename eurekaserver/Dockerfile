# eurekaserver/Dockerfile

# 使用Java 8官方镜像（Alpine精简版）
FROM openjdk:8-jre-alpine

# 设置时区（上海）
ENV TZ=Asia/Shanghai
RUN apk add --no-cache tzdata && \
    ln -sf /usr/share/zoneinfo/$TZ /etc/localtime && \
    echo $TZ > /etc/timezone

# 创建非root用户
RUN addgroup -S spring && adduser -S spring -G spring
USER spring

# 设置工作目录
WORKDIR /app

# 复制JAR文件（注意使用具体的版本号）
COPY --chown=spring:spring target/eurekaserver-1.0-SNAPSHOT.jar app.jar

# 暴露Eureka端口（与application.yml一致）
EXPOSE 8761

# 健康检查（需要Actuator依赖）
HEALTHCHECK --interval=30s --timeout=3s \
    CMD wget --quiet --tries=1 --spider http://192.168.196.100:8761/actuator/health || exit 1

# 启动命令（Java 8优化参数）
ENTRYPOINT ["java", \
    "-Djava.security.egd=file:/dev/./urandom", \
    "-Xmx512m", \
    "-jar", \
    "app.jar"]
