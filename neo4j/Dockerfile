FROM neo4j:latest

ENV NEO4J_AUTH=neo4j/${NEO4J_PASSWORD}

# Copy custom configuration file into the correct location
COPY conf/neo4j.conf /var/lib/neo4j/conf/

EXPOSE 7474 7687

RUN ls -la /var/lib/neo4j/conf/
RUN cat /var/lib/neo4j/conf/neo4j.conf