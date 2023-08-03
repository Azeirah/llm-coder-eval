# Prompts

This document is a list of all prompts included in the evaluation template. It's meant to grow over time.

Prompts are grouped by programming language or technology (ie, "web", "typescript", "Golang", "Linux commandline", "Embedded", ...)

## General performance and "saneness"

### Story time

```
Tell a short story about the worst bug you've had to fix in your career.
```

This prompt is meant to test the model's coherence and output speed. It's a good test if the model is "sane"

### Web

#### React click outside element hook in TypeScript

```
Write a react useOnClickOutsideElement(elementRef, onClick) function in typescript
```

This prompt is meant to test its coding abilities. This task is more specific than regular coding challenges like "sum a list" and can be relevant in daily work. The output should be tested in a real React project.

- Does it provide valid typescript?
- Does the hook work?
- Did it use `getBoundingClientRect()` or node.contains? `node.contains` is preferable but both are ok.
- Does it include `touchstart` for mobile when it uses `mousedown`?

A good answer looks like:

```tsx
export function useOnClickOutsideElement(elementRef: React.RefObject<HTMLElement>, onClick: () => void): void {
  useEffect(() => {
    const handleClickOutside = (event: MouseEvent | TouchEvent) => {
      if (elementRef.current && !elementRef.current.contains(event.target as Node)) {
        onClick();
      }
    };

    document.addEventListener("mousedown", handleClickOutside);
    document.addEventListener("touchstart", handleClickOutside);

    return () => {
      document.removeEventListener("mousedown", handleClickOutside);
      document.removeEventListener("touchstart", handleClickOutside);
    };
  }, [elementRef, onClick]);
}
```

#### Add a basic testing method

```ts
export class Feedback {
  expectMessageForUser() {
  	cy.get(".Toastify").should("exist");
  	cy.get(".Toastify__toast-body").click();
  }

  expectSuccessMessage() {
  	cy.get(".Toastify__toast--success").should("exist").click();
  }

  expectErrorMessage() {
  	cy.get(".Toastify__toast--error").should("exist").click();
  }
}
```

- The answer should add the method to the existing code or provide the method standalone without the class surrounding it

A good answer looks like:

```tsx
expectWarningMessage() {
  cy.get(".Toastify__toast--warning").should("exist").click();
}
```

### Linux commandline

#### Find files

```
Write a command to find all html files in all directories on ubuntu
```

- Does the model pass the test?
	- `find / -type f -name "*.html"` is one correct answer
