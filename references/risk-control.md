# Risk Control Reference

For each phase identify:
- Data that could be changed or lost
- External state that could be affected
- Behavior that could regress
- How to detect failure
- How to roll back without rewriting user data

Use stronger checks for migrations, authentication, payment, concurrency, public APIs, or irreversible operations.
