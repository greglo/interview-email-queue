# Email Queue Interview

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
