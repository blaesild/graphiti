FROM neo4j:latest
ENV NEO4J_AUTH=neo4j/${NEO4J_PASSWORD}

# Copy custom configuration file
COPY neo4j.conf /var/lib/neo4j/conf/

EXPOSE 7474 7687
