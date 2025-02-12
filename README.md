# gRPC User and Garage Services

This project demonstrates a simple gRPC implementation with two services: User Service and Garage Service.

## Prerequisites

- Go 1.16 or later
- Protocol Buffers compiler (protoc)
- Go plugins for protocol buffers

## Installation

1. Install protoc compiler
2. Install Go protobuf plugins

 ```sh
go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
```

## Generate Proto Files

Run the following commands from the project root:

```sh
protoc --go_out=. --go_opt=paths=source_relative \
    --go-grpc_out=. --go-grpc_opt=paths=source_relative \
    common/model/*.proto
```

### Running the Services

1. Start the User Service:

```sh
go run services/service-user/main.go
```

2. Start the Garage Service in a new terminal:

```sh
go run services/service-garage/main.go
```

3. Run the client to test both services:

```sh
go run client/main.go
```
 ### Project Structure

 ```plaintext
 .
├── common/
│   ├── config/
│   └── model/
│       ├── user.proto
│       └── garage.proto
├── services/
│   ├── service-user/
│   └── service-garage/
└── client/
```

## Learning Resources

For more information and learning resources about gRPC and Protocol Buffers in Go, you can refer to the following link:

- [Dasar Pemrograman Golang - gRPC dan Protocol Buffers](https://dasarpemrogramangolang.novalagung.com/C-golang-grpc-protobuf.html)