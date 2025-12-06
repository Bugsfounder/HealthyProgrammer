# Contributing to BreakTimer

Thanks for your interest in contributing!  
This project is built with Rust + Tauri and aims to be a lightweight,  
cross-platform productivity app.  
Please read the guidelines below before submitting changes.

## 🛠 Getting Started

1. Fork the repository
2. Clone your fork
3. Create a feature branch  
   Example: `git checkout -b feature/timer-engine`
4. Run the project in development mode:

```

cargo tauri dev

```

## ✔ Code Guidelines

### **Rust Backend**

- Keep modules small and readable
- Document public functions
- Avoid blocking operations in the main thread
- Use `tokio`/async where helpful
- Prefer returning `Result<T, E>` over panicking

### **Frontend**

- Keep UI clean and minimal
- Avoid adding heavy JS dependencies
- Place components in logical folders

## Testing

- Test core logic in Rust (timer, shortcuts, notifications)
- UI tests are optional but appreciated
- Every PR must run without errors on:
- Linux
- Windows (if available)
- macOS (optional)

## Pull Requests

Before submitting a PR:

- Make sure code compiles
- No unused imports / warnings
- Keep changes focused — one PR per feature
- Write a short description of what your PR does
- Reference the related issue number

Example commit message:

```

feat(timer): implement background timer loop with notifications

```

## Labels We Use

| Label              | Meaning                    |
| ------------------ | -------------------------- |
| `good first issue` | Simple tasks for beginners |
| `bug`              | Something isn’t working    |
| `feature`          | New functionality          |
| `enhancement`      | Improve existing code/UI   |
| `docs`             | Documentation updates      |
| `help wanted`      | We need contributors       |

## Branch Strategy

- `main` → stable release
- `dev` → active development
- Feature branches → merged via PR

Naming examples:

```

feature/global-shortcut
fix/sound-error
docs/readme-update

```

## Communication

If you're unsure about anything:

- Open an issue
- Ask before starting a large feature
- Keep discussions respectful and focused

## Thank You

Every contribution — big or small — helps make BreakTimer better.  
We appreciate your time and effort!
