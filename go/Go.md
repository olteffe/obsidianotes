**Update go version & modules**

```bash
go mod edit -go=1.17
go get -u ./…
go mod tidy
```
***

**gRPC**

```bash
go get -u google.golang.org/grpc
```
***

**openapi generator**

```bash
docker run --rm -v "${PWD}:/local" openapitools/openapi-generator-cli generate \
	-i /local/openapi.yaml \
	-g go-echo-server \
	-o /local/out/go

```
***

**Go offline doc**
1. install "go-tools"
2. run
		godoc -http :8000

3. open 
http://localhost:8000/pkg/testing/
***

