# hook workflow action

Хукает другие workflow которые с типом dispatch

## Примеры

### хукаем два workflow

```yaml
# nosemgrep
- uses: tapclap/hook-workflow-action@main
  id: build-images
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}
    workflows: |
    - workflow1.yaml
    - workflow2.yaml
```

### Тоже самое но в json формате

```yaml
# nosemgrep
- uses: tapclap/hook-workflow-action@main
  id: build-images
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}
    workflows: |
      [
        "workflow1.yaml",
        "workflow2.yaml"
      ]
```

### json в одну строку

```yaml
# nosemgrep
- uses: tapclap/hook-workflow-action@main
  id: build-images
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}
    workflows: '["workflow1.yaml", "workflow2.yaml"]'
```


## Inputs

### `github_token`
github token для того чтобы хукнуть workflow

### `workflows`
Список workflows в yaml или json формате
