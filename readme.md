# setup-git-app-user

> GitHub Action that sets git user and email using an app id and private key

If you try to use `git commit` or `git tag` on GitHub Actions, it will throw an error:

<img src="https://user-images.githubusercontent.com/1402241/96522622-59905880-1239-11eb-9993-07b64bebb282.png" alt="Please tell me who you are. Run git config to set your account's default identity" width="489">

This is a convenience action which sets the user and email in a few lines.

# Usage

```yaml
    steps:
      - uses: actions/checkout@v4
      - uses: spotdemo4/setup-git-app-user@v1
        with:
          app-id: ${{ vars.CLIENT_ID }}
          private-key: ${{ secrets.PRIVATE_KEY }}
      - run: git commit --message 'Something cool'
      - run: git push
```

Forked from [setup-git-user](https://github.com/fregante/setup-git-user)