# 使用 OpenJDK 8 基础镜像
FROM openjdk:8-jre-alpine

# 设置工作目录
WORKDIR /app

# 复制构建好的 JAR 文件到容器中
COPY target/gateway-service-0.0.1-SNAPSHOT.jar /app/gateway-service.jar

# 暴露应用端口
EXPOSE 8050

# 启动应用
ENTRYPOINT ["java", "-jar", "gateway-service.jar"]
