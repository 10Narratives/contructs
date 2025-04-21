# Protocol Buffers Contracts Repository

This repository contains Protocol Buffers (`.proto`) files that define the data structures and service interfaces for various services. These `.proto` files serve as contracts between clients and servers in a gRPC-based architecture.

## Overview

This repository is dedicated to hosting `.proto` files that define the APIs for different services. Each service has its own directory under the `contracts` folder, and the `.proto` files are organized accordingly.

The `contracts/ddb` directory contains the `.proto` file for the `Worker` service, which provides CRUD operations for managing documents in a distributed database.

### Worker Service

The `Worker` service provides CRUD operations for managing documents in a distributed database. Below is a detailed description of each method:

#### Create

| Field        | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| **Method**   | `rpc Create(CreateRequest) returns (CreateResponse)`                        |
| **Purpose**  | Creates a new document in the specified collection.                         |
| **Request**  | `CreateRequest`                                                             |
|              | - `collection_id`: The ID of the collection where the document will be created. |
|              | - `payload`: A map of key-value pairs representing the document's content.  |
| **Response** | `CreateResponse`                                                            |
|              | - `status`: The status code of the operation.                              |
|              | - `document`: The created document.                                        |

#### Read

| Field        | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| **Method**   | `rpc Read(ReadRequest) returns (ReadResponse)`                              |
| **Purpose**  | Retrieves a single document by its ID from the specified collection.        |
| **Request**  | `ReadRequest`                                                               |
|              | - `collection_id`: The ID of the collection.                                |
|              | - `document_id`: The ID of the document to retrieve.                        |
| **Response** | `ReadResponse`                                                              |
|              | - `status`: The status code of the operation.                              |
|              | - `document`: The retrieved document.                                      |

#### ReadAll

| Field        | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| **Method**   | `rpc ReadAll(ReadAllRequest) returns (ReadAllResponse)`                     |
| **Purpose**  | Retrieves all documents from the specified collection.                      |
| **Request**  | `ReadAllRequest`                                                            |
|              | - `collection_id`: The ID of the collection.                                |
| **Response** | `ReadAllResponse`                                                           |
|              | - `status`: The status code of the operation.                              |
|              | - `documents`: A list of all documents in the collection.                   |

#### Update

| Field        | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| **Method**   | `rpc Update(UpdateRequest) returns (UpdateResponse)`                        |
| **Purpose**  | Updates an existing document in the specified collection.                   |
| **Request**  | `UpdateRequest`                                                             |
|              | - `collection_id`: The ID of the collection.                                |
|              | - `document_id`: The ID of the document to update.                          |
|              | - `payload`: A map of key-value pairs representing the updated content.     |
| **Response** | `UpdateResponse`                                                            |
|              | - `status`: The status code of the operation.                              |

#### Delete

| Field        | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| **Method**   | `rpc Delete(DeleteRequest) returns (DeleteResponse)`                        |
| **Purpose**  | Deletes a document from the specified collection.                           |
| **Request**  | `DeleteRequest`                                                             |
|              | - `collection_id`: The ID of the collection.                                |
|              | - `document_id`: The ID of the document to delete.                          |
| **Response** | `DeleteResponse`                                                            |
|              | - `status`: The status code of the operation.                              |
