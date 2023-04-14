# API Endpoint Documentation: /health

The `/health` endpoint checks the status of the server and returns the name of the printer. It is a GET endpoint and does not require any parameters.

## Endpoint URL


```
GET http://localhost:3000/health
```

## Output Data

```
{
"printerName": "MyPrinter"
}
```

## Example Usage

```
curl http://localhost:3000/health
```

## Error Handling

- `200 OK` - The request was successful and the document was printed.
- `400 Bad Request` - The request was malformed or missing required parameters.
- `404 Not Found` - The requested resource was not found.
- `500 Internal Server Error` - An unexpected error occurred on the server.\








# API Endpoint Documentation: /print

The `/print` endpoint is a POST method API that takes in a JSON data with two fields, `name` and `base64`, and prints the decoded contents of the `base64` field to the console.

## Endpoint URL


```
POST http://localhost:3000/print
```

## Input Data

The endpoint expects a JSON data with the following two fields:

```
{
"name": "example.txt",
"base64": "SGVsbG8gV29ybGQh..."
}
```

- `name` (string): the name of the file to be printed
- `base64` (string): the base64 encoded contents of the file

## Output Data

The endpoint saves file to the `files` directory and print it to the default printer.

## Example Usage

```
curl -X POST -H "Content-Type: application/json" -d '{"name":"example.txt", "base64":"SGVsbG8gV29ybGQh"}' http://localhost:3000/print
```


This will print the decoded contents of the `base64` field to the default printer

## Error Handling

If the endpoint receives an invalid request or fails to print the file, it will return an appropriate error message.\






# API Endpoint Documentation: /test

The `/test` allows the user to browse and post a file to the /print endpoint. It returns an HTML page with a file upload form.

## Endpoint URL


```
http://localhost:3000/test
```


