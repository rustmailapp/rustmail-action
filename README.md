# RustMail Action

Start a RustMail SMTP catcher and assert on captured emails in CI.

## Usage

```yaml
# 1. Start the server
- uses: rustmailapp/rustmail-action@v1

# 2. Run your tests (they send email to localhost:1025)
- run: npm test

# 3. Assert on captured emails
- uses: rustmailapp/rustmail-action@v1
  with:
    mode: assert
    assert-count: 1
    assert-subject: "Welcome"
```

## Inputs

### Start Mode (default)

| Input | Default | Description |
|-------|---------|-------------|
| `smtp-port` | `1025` | SMTP port |
| `http-port` | `8025` | HTTP/API port |
| `version` | `latest` | RustMail release version |

### Assert Mode

| Input | Default | Description |
|-------|---------|-------------|
| `assert-count` | `1` | Minimum matching emails |
| `assert-subject` | — | Filter by subject |
| `assert-sender` | — | Filter by sender |
| `assert-recipient` | — | Filter by recipient |

## Outputs

| Output | Description |
|--------|-------------|
| `http-port` | HTTP port the server is listening on |
| `smtp-port` | SMTP port the server is listening on |

## Platforms

Linux (x86_64, arm64) and macOS (x86_64, arm64).

## License

MIT or Apache-2.0
