# Conditional Git Configuration

## Separate work and private git configs

For work I want my git user name and email different from my personal github repos. The global `.gitconfig` can use [includeIf](https://news.ycombinator.com/item?id=38942892) to achieve this.

```ini
[includeIf "gitdir:~/work/"]
    path = ~/work/.gitconfig
[includeIf "gitdir:~/personal/"]
    path = ~/personal/.gitconfig
```

Then inside repos in the respective folder the work or personal config is also used. There we set user and email.

```ini
[user]
        name = your name
        email = name@example.com
```
