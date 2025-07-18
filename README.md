# Email Queue Interview

You're building an AI system that processes incoming emails. Emails arrive rapidly and must be consumed in parallel, but messages belonging to the same thread must be processed serially to preserve context.

Implement an `EmailQueue` that ensures:

1. **Parallel processing** – email processors should be assigned work as soon as they are free (if there is an unprocessed email).
2. **Dependency ordering** — an email with a `parentId` is not processed until its parent email has completed.
3.  **FIFO** — if multiple emails are eligible to be consumed, the one received first should be processed.



```ts

export interface Email {
  id: string;
  parentId?: string;
  subjectLine: string;
}

export type EmailProcessor = (email: Email) => Promise<void>

export abstract class EmailQueue {
  constructor(processors: EmailProcessor[]) {}
  abstract addToQueue(email: Email): void
}

```
