# First AI interaction

## Architecture and Best Practices

Successful AI integration in 4D applications follows established architectural patterns that promote maintainability, reliability, and scalability.

### Class-Based Architecture

Organizing AI functionality into dedicated classes provides clear separation of concerns. Each class handles a specific domain: document analysis, summarization, conversation management, or configuration. This approach encapsulates AI logic, making code easier to test, maintain, and extend.

### Asynchronous Processing Pattern

AI API calls can take several seconds to complete. Processing these calls in worker processes prevents UI freezing and maintains application responsiveness. The pattern involves launching a worker process for AI operations, updating the database with results, and using timer-based polling in the UI process to reflect changes.

**Note: **4D AIKit provides a native asynchronous call pattern using callbacks (see [Asynchronous
Call](https://developer.4d.com/docs/aikit/asynchronous-call)). 
However, this approach only works within the current process. For multi-process cases, use **`CALL WORKER`** or `**CALL FORM**` instead.