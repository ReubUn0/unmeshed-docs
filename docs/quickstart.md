---
title: Quickstart - write your first Unmeshed worker
description: Install the Unmeshed SDK for Python, TypeScript, Go or Java and register your first worker.
---

# Quickstart: write your first worker

A worker is a plain function. When a running process reaches a step with the same name, Unmeshed calls your function with that step's input and records the output.

!!! tip "Before you start"
    Sign up at [unmeshed.io](https://unmeshed.io/) and [generate client credentials](https://unmeshed.io/docs/sdks/creating-client-credentials) to get your client ID and auth token.

=== "Python"

    ```bash
    pip install unmeshed-sdk
    ```

    ```python
    from unmeshed.sdk.configs.client_config import ClientConfig
    from unmeshed.sdk.unmeshed_client import UnmeshedClient
    from unmeshed.sdk.apis.workers.worker import Worker

    def sample_function(input_dict: dict) -> dict:
        return {"message": "Hello, world!", "input_received": input_dict}

    client_config = ClientConfig()
    client_config.set_client_id("your-client-id")
    client_config.set_auth_token("your-auth-token")
    client_config.set_base_url("http://localhost")
    client_config.set_port(8080)

    client = UnmeshedClient(client_config)
    client.register_worker(
        Worker(execution_method=sample_function, name="sample_function",
               namespace="default", max_in_progress=100)
    )
    client.start()
    ```

    Full guide: [Python SDK](https://unmeshed.io/docs/sdks/python-sdk)

=== "TypeScript / JS"

    ```bash
    npm install @unmeshed/sdk
    ```

    ```javascript
    const { UnmeshedClient } = require('@unmeshed/sdk');

    const unmeshedClient = new UnmeshedClient({
      baseUrl: 'http://localhost',
      port: 8080,
      authToken: 'your-auth-token',
      clientId: 'your-client-id',
    });

    const workerFunction = async (input) => ({ ...(input || {}), ranAt: new Date() });

    unmeshedClient.startPolling([
      { worker: workerFunction, namespace: 'default', name: 'test-node-worker', maxInProgress: 500 },
    ]);
    ```

    Full guide: [JavaScript/TypeScript SDK](https://unmeshed.io/docs/sdks/javascript-typescript-sdk)

=== "Go"

    ```bash
    go get github.com/unmeshed/unmeshed-go-sdk
    ```

    ```go
    package main

    import (
        "fmt"
        apis "github.com/unmeshed/unmeshed-go-sdk/sdk/apis/main"
        apis2 "github.com/unmeshed/unmeshed-go-sdk/sdk/apis/workers"
        "github.com/unmeshed/unmeshed-go-sdk/sdk/configs"
    )

    func MyWorker(data map[string]interface{}) string {
        return "Hello, Unmeshed!"
    }

    func main() {
        cfg := configs.NewClientConfig()
        cfg.SetClientID("your-client-id")
        cfg.SetAuthToken("your-auth-token")
        cfg.SetBaseURL("http://localhost")
        cfg.SetPort(8080)

        client, err := apis.NewUnmeshedClient(cfg)
        if err != nil {
            fmt.Printf("Error creating client: %v\n", err)
            return
        }
        client.RegisterWorker(apis2.NewWorker(MyWorker, "my-worker"))
        client.Start()
    }
    ```

    Full guide: [Go SDK](https://unmeshed.io/docs/sdks/go-sdk)

=== "Java"

    Requires Java 21+. Start from the example project:

    ```bash
    git clone https://github.com/unmeshed/java-sdk-example.git
    ```

    ```java
    import io.unmeshed.client.workers.WorkerFunction;

    public class YourClass {

        @WorkerFunction(name = "exampleWorker")
        public WorkerOutput exampleMethod(WorkerInput input) {
            // Your worker logic here; return a typed output
        }
    }
    ```

    Full guide: [Java SDK](https://unmeshed.io/docs/sdks/java-sdk)

## Next steps

- Add your worker as a step in a process definition: see [Process Definition](https://unmeshed.io/docs/refs/process-definition).
- Browse the [step types](step-types.md) you can combine with it.
- Read the official [Getting Started guide](https://unmeshed.io/docs/start-here/getting-started).
