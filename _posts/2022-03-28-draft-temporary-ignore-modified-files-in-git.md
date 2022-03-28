---
layout: post
title: Temporary ignore any changes done to a file in git
---



There a cirmcumtances wherein when you are working on a local git repo, and you wanted to temporary modify an existing file but don't want git to recognize any changes on that file. The easest way to do this  are as follows

```bash
%> git update-index --assume-unchanged [path/to/file] 
```

For example,

```bash
%> git update-index --assume-unchanged users_controller.rb
```

Once you do this, when you a `git status` command, git will not pickup the changes you done in `users_controller.rb`. Once you are done with temporary modifying the file you want for get to temporary ignores the changes, you can issue another git command that will change back to git to monitor any changes on a specific file. The comand for this would look something like this,

```bash
$> git update-index --no-assume-unchanged [path/tofile]
```

And should look like this, for example,

```bash
%> git update-index --no-assume-unchanged user_controller.rb
```

Once you turn run the above command, git will now monitor any changes on the file you specified.
