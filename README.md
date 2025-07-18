# Email Queue Interview

Implement `EmailQueue` such that
1. Emails are processed in the order in which they are received
2. Emails should not be processed until their parentId email is processed

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
