# Multiple actions in a single repository
This repository showcases how to put multiple actions in a single repository.

## Contents

This repository contains two actions:
* start
* stop
They both run a short shell script to show that each of them is running and they can work on the same file system.

## Structure

```
├── .github
│   └── workflows       # Workflow files that use your actions
│       └── example-workflow.yml
├── start
│   └── action.yml      # First action is defined here
├── stop
│   └── action.yml      # Second action is defined here
└── README.md
```

## Referencing the two actions
You can separately run/reference the two actions in your workflows like the way it is shown in the `.github/workflows/example-workflow.yml`

See here:
```yaml
jobs:
  multi-action-job:
    runs-on: ubuntu-latest
    steps:
      - uses: slashben/multiple-actions-example/start@main
        name: Start Script
      - uses: slashben/multiple-actions-example/stop@main
        name: Stop Script
```

