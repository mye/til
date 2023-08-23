# change how conda modifies the prompt

I use a mostly colorless terminal setup but wanted a colored block before the prompt. Conda interfered by putting it's environment indicator in front of it.

In `.condarc` set `env_prompt: \[\e[43m\] \[\e[0m\] ({default_env})`. Then put a conditional inside you shell prompt to check for active environments:

```
export PS1="\$( [ -z \"\$CONDA_DEFAULT_ENV\" ] && echo '\[\e[43m\] \[\e[0m\]') \w \$(parse_git_branch)\n\[\e[43m\] \[\e[0m\] "
```

Now the colored block is shown correctly whether or not an environment is active.
