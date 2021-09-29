### GitHub Actions による自動生成

- develop ブランチにマージされたタイミングで main ブランチへの PR が workflow により作成される。
  - git-pr-release を利用
- main ブランチにマージされたタイミングで Release とタグが workflow により作成される。
  - PR のタイトルがそのままタグ名になる
  - PR の内容がそのまま Release の内容になる

### ghch・gitHub-release を使った手動生成

```
github-release release \
  --user github_user_name \
  --repo repository_name \
  --tag vX.X.X \
  --name "vX.X.X" \
  --description "$(ghch --format=markdown --latest)"
```
