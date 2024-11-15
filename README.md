# Jarvis action status report action

This action send telegram message with action status

## Usage

Here's an example of how to use this action in a workflow file:

```yaml
name: Example Workflow
jobs:
  lint:
    name: Lint
    runs-on: ubuntu-latest
    steps:
      - name: Check rubocop
        run: bundle exec rubocop
      - uses: rubycats-com/jarvis-report-action@main
        if: success() || failure()
        with:
          report-to: ${{ secrets.JARVIS_TELEGRAM_REPORT_TO }}
          token: ${{ secrets.JARVIS_TELEGRAM_TOKEN }}
```

## Inputs

| Input       | Required | Description        |
|-------------|----------|--------------------|
| `report-to` | true     | Telegram chat id   |
| `token`     | true     | Telegram bot token |

## Outputs

No outputs in this action
