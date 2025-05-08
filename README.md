## Exploring Clean Architecture: ExpenseTracker

A project to learn the ropes of domain-based architecture for iOS applications to improve separation of concerns and testability. Since all layers are separate, tests for all parts were able to be written separately and concisely. **See the flowchart below for the layer design.**

### Implementation

- Clean MVVM + **Repository** pattern with protocol-based data access
- **Domain** layer for holding models and protocols
- `Swift 6` Complete Concurrency Checking
- Single source of truth for shared data (`actor`-based storage)
- Support for multiple data sources (`InMemory`, `SwiftData`)
- _ViewModels_ expose `async` methods instead of handling Tasks
- `Swift Testing` suite with full coverage of _Services_, _ViewModels_ and _Repositories_
- Simple dependency injection using a `ViewModelFactory`

### Architecture

```
+---------------+-----------------+
|      UI       | - Views         |
+---------------+-----------------+
                v
+---------------+-----------------+
|               | - Models        |
|  Application  | - Services      |
|               | - ViewModels    |
+---------------+-----------------+
                v
+---------------+-----------------+
|               | - Models        |
|    Domain     | - Repositories  |
|               |                 |
+---------------+-----------------+
                ^
+---------------+----------------------+
|               | - Repositories       |
|     Data      | - DataSources + DTO  |
|               | - Storages           |
+---------------+----------------------+
```
