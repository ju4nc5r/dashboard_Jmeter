# Utiliza Alpine como base
FROM alpine:latest

# Establece variables de entorno
ENV JMETER_VERSION 5.6.3
ENV JMETER_HOME /opt/jmeter
ENV PATH $JMETER_HOME/bin:$PATH


# Actualiza paquetes e instala dependencias necesarias
RUN apk update && apk add --no-cache 
RUN apk add openjdk17-jre 
RUN apk add curl 
RUN apk add tar
RUN apk add bash
RUN apk add vim
RUN mkdir $JMETER_HOME
RUN curl -sSL https://downloads.apache.org/jmeter/binaries/apache-jmeter-5.6.3.tgz | tar -xz -C $JMETER_HOME/
RUN mkdir -p $JMETER_HOME/apache-jmeter-5.6.3/test
COPY test_scripts/ $JMETER_HOME/apache-jmeter-5.6.3/test/


# Configura el directorio de trabajo
WORKDIR $JMETER_HOME

# Define el comando por defecto
CMD ["jmeter"]
