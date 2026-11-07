FROM python:3.9-slim

RUN apt-get update && apt-get install -y apache2-utils

COPY make-data.py .
RUN python3 make-data.py
COPY generate-votes.sh .
CMD ["bash", "generate-votes.sh"]
