## how to trace in golang

Please make sure you have docker-compose in your compute.
- deploy es+kibana
  - exec `docker-compose -f docker-es-kibana.yml up -d`
  - visit at http://localhost:5601
- deploy jaeger-collector
  - `docker-compose -f docker-jaeger-collector.yml up -d`
- deploy jaeger-query UI && Service
  - exec `docker-compose -f docker-jaeger-query.yml up -d`
  - visit at http://localhost:16686
- deploy opentelemetry collector
  - exec `docker-compose -f docker-otel-collector.yml up -d`
- run go server && push your data into this.
  - `go run .`
- finally,you will see your test data in http://localhost:16686.

### Note
However,you need change `localhost` in those files into `your inner domain ip`,otherwise you cannot visit these middlewares. 
