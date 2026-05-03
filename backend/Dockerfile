FROM python:3.10.1

WORKDIR /app

EXPOSE 9000

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt 

COPY . .

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]

CMD ["gunicorn", "kittygram_backend.wsgi:application", "--bind", "0.0.0.0:9000"]