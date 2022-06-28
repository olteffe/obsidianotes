```yml
go-test:
    name: Unit tests
    runs-on: ubuntu-20.04
    steps:
      - uses: actions/setup-go@v2
        with: {go-version: 1.17}

      - uses: actions/checkout@v2

      - name: Go modules Cache # Docs: <https://git.io/JfAKn#go---modules>
        uses: actions/cache@v2
        id: go-cache
        with:
          path: ~/go/pkg/mod
          key: ${{ runner.os }}-go-${{ hashFiles('**/go.sum') }}
          restore-keys: ${{ runner.os }}-go-

      - if: steps.go-cache.outputs.cache-hit != 'true'
        run: go mod download

      - name: Run Unit tests
        run: go test -race ./...
```