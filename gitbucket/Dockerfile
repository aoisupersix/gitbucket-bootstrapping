# 公式のイメージより細かいバージョニングをしたいので別にDockerfileを作ってる
FROM java:8-jre

ADD https://github.com/gitbucket/gitbucket/releases/download/4.32.0/gitbucket.war /opt/gitbucket.war

RUN ln -s /gitbucket /root/.gitbucket

VOLUME /gitbucket

# Port for web page
EXPOSE 8080
# Port for SSH access to git repository (Optional)
EXPOSE 29418

ENV MAX_FILE_SIZE=3145728

CMD ["sh", "-c", "java -jar /opt/gitbucket.war --max_file_size=$MAX_FILE_SIZE"]