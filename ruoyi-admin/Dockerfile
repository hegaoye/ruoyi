FROM openjdk:8-jdk-alpine
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
VOLUME /tmp
ADD ruoyi-admin/target/ruoyi-admin.jar app.jar
RUN apk add --update font-adobe-100dpi ttf-dejavu fontconfig
ENV JAVA_OPTS="-Xms256m"
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /app.jar" ]
EXPOSE 8080


