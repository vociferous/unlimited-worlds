# Source Code

All game source code. Empty until Phase 1 begins — tech stack selection in Phase 0 will determine the language and structure here.

## Structure (planned)

```
src/
├── client/       # Game client — rendering, UI, input handling, audio
├── server/       # Game server — world simulation, netcode, persistence, auth
├── shared/       # Shared logic — entity definitions, network protocol, constants
└── tools/        # Dev tools — map editor, asset pipeline, debug utilities
```

## Prerequisites

Tech stack is unselected. See:
- `progress/decisions/` for ADRs once made
- `docs/technical/` for architecture specs

## Code Standards

To be defined once the tech stack is chosen. Will cover:
- Language-specific style guide
- Testing requirements
- Performance budgets
- Security requirements (anti-cheat, auth, input validation)
