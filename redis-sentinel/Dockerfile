FROM redis:latest

ARG REDIS_PORT \
    REDIS_MASTER_PORT \
    REDIS_MASTER_HOST

COPY sentinel.conf /etc/redis/sentinel.conf

RUN sed -i 's/REDIS_PORT/'$REDIS_PORT'/g' /etc/redis/sentinel.conf  && \
    sed -i 's/REDIS_MASTER_HOST/'$REDIS_MASTER_HOST'/g' /etc/redis/sentinel.conf  && \
    sed -i 's/REDIS_MASTER_PORT/'$REDIS_MASTER_PORT'/g' /etc/redis/sentinel.conf 
    
ENTRYPOINT redis-sentinel /etc/redis/sentinel.conf

