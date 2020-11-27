FROM nginx

RUN apt-get update
RUN apt-get install -y python
RUN echo 1.0 >> /etc/version && apt-get install -y git && apt-get install -y iputils-ping

RUN mkdir app
COPY app /app
WORKDIR /app
RUN touch config
RUN echo "npm install"

ADD test test-app
ADD https://raw.githubusercontent.com/Fernando-Cusco/configuraciones-kubernetes/master/README.md test-app

ENV dir=/configuraciones
RUN mkdir $dir

CMD ["nginx", "-g", "daemon off;"]
COPY app/index.html /usr/share/nginx/html
EXPOSE 80

VOLUME ["/usr/share/nginx/html"]

#CMD echo "Bienvenidos al container de Python modo shell"
#ENTRYPOINT ["/bin/bash"]
