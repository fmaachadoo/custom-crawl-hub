FROM python:3.11-slim

WORKDIR /app

RUN pip install hatch

COPY pyproject.toml ./

RUN hatch python install all

RUN hatch python update all

COPY . .

EXPOSE 8000

CMD ["hatch", "run", "mkdocs", "serve", "-a", "0.0.0.0:8000", "-f", "./src/mkdocs.yml"]

