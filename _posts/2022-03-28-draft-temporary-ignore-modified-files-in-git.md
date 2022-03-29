---
layout: post
title: Temporary ignore any changes done to a file in git
---

When you are working with a project that uses `git`, and for some reason you need to temporary modify one of the files being managed by `git`, and you don't want to bother adding it to the `.gitignore` config file, one trick that I found was to use the following command

```tex
git update-index --assume-unchanged [path/to/file] 
```

here's an example of how to actually use it

```bash
vulcansmithy@auth-service ~ %> git update-index --assume-unchanged  app/controller/susers_controller.rb
```

And once you're good and wanted to revert back to the previous behavior, just use the command below to  have git monitor again any changes for the file you specified

```tex
git update-index --no-assume-unchanged [path/tofile]
```

Here's an actual example of how the above command could be used

```bash
vulcansmithy@auth-service ~ %>  git update-index --no-assume-unchanged app/controller/susers_controller.rb
```

