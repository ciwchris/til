When starting the Elixir interactive shell informational text is displayed instructing users how to
exit, `Ctrl-C`. Upon pressing `Ctrl-C` the shell does not immediately exit but instead displays a
list of commands to execute next. To actually exit type `a`. This workflow made me feel I was
missing something, and that there should be a way to exit the shell immediately.

I next came across `Ctrl-G`, which drops the users into the 'User switch command'. Type `h` to
display a list of commands. `q` can be used to exit, 'quit', the shell. There still seemed like
there had to be another way.

Finally I came across the article [How to quit the Elixir shell
(IEx)?](http://blog.plataformatec.com.br/2016/03/how-to-quit-the-elixir-shell-iex). The article
discusses the above two commands but then goes on to list a third, `Ctrl-\`. Finally, the command I
was searching for!
