# setup-git-app-user

> GitHub Action that sets `git config user.name` and `git config user.email` using an app id and private key.

# Usage

```yaml
    steps:
      - uses: actions/checkout@v4
      - uses: spotdemo4/setup-git-app-user@v2
        with:
          app-id: ${{ vars.CLIENT_ID }}
          private-key: ${{ secrets.PRIVATE_KEY }}
      - run: git commit --message 'Something cool'
      - run: git push
```

or just get the output:

```yaml
    steps:
      - uses: actions/checkout@v4
      - uses: spotdemo4/setup-git-app-user@v2
        id: app-user
        with:
          app-id: ${{ vars.CLIENT_ID }}
          private-key: ${{ secrets.PRIVATE_KEY }}
      - run: echo ${{ steps.app-user.outputs.name }}
      - run: echo ${{ steps.app-user.outputs.email }}
```

Forked from [setup-git-user](https://github.com/fregante/setup-git-user)