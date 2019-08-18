FROM openjdk:8u201-jdk-alpine3.9
LABEL maintainer="Evan Lalopoulos <el17604@my.bris.ac.uk>"

WORKDIR /opt/

# Download stanford corenlp
RUN wget http://nlp.stanford.edu/software/stanford-corenlp-full-2018-10-05.zip && \
    unzip stanford-corenlp-full-2018-10-05.zip && \
    rm stanford-corenlp-full-2018-10-05.zip

WORKDIR /opt/stanford-corenlp-full-2018-10-05

# Download english model
RUN wget http://nlp.stanford.edu/software/stanford-english-corenlp-2018-10-05-models.jar

# Download extra resources needed to run relation extraction and entity linking
RUN wget http://nlp.stanford.edu/software/stanford-english-kbp-corenlp-2018-10-05-models.jar

ENV JAVA_XMX 2g
ENV THREADS 2
ENV PORT 9000
EXPOSE $PORT

# Start CoreNLP server (https://stanfordnlp.github.io/CoreNLP/corenlp-server.html)
CMD java -Xmx$JAVA_XMX -cp "*" edu.stanford.nlp.pipeline.StanfordCoreNLPServer -port $PORT -threads $THREADS -timeout 15000
