FROM nginx

COPY wait-for-it.sh /
CMD ["/wait-for-it.sh", "logstash:5044", "--", "nginx", "-g", "daemon off;"]
