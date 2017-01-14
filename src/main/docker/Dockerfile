FROM java:openjdk-8-jre-alpine
RUN echo "Asia/Shanghai" > /etc/timezone

# add directly the war
ADD *.war /registry.war

RUN sh -c 'touch /registry.war'
EXPOSE 8761
VOLUME /tmp

ENV SPRING_PROFILES_ACTIVE=prod,git
ENV GIT_URI=https://github.com/xunniao-tech/xunniao-registry.git
ENV GIT_NAME=wujun27@163.com
ENV GIT_PASS=wujun1986
ENV GIT_SEARCH_PATHS=central-config

CMD ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/tenbent-registry.war","--spring.cloud.config.server.git.uri=${GIT_URI}","--spring.cloud.config.server.git.username=${GIT_NAME}","--spring.cloud.config.server.git.password=${GIT_PASS}","--spring.cloud.config.server.git.search-paths=${GIT_SEARCH_PATHS}"]
