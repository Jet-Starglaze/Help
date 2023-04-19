```py
  @commands.command()
  async def imgtest(self, ctx):
    our_list = ['https://cdn.pixabay.com/photo/2017/02/20/18/03/cat-2083492__340.jpg', 'https://cdn.pixabay.com/photo/2017/02/20/18/03/cat-2083492__340.jpg']
    p = SimplePagesImages(entries=our_list, per_page=1, ctx=ctx)
    p.embed.colour = 0xF02D7D
    await p.start()
```

error
```
discord.ext.commands.errors.CommandInvokeError: Command raised an exception: HTTPException: 400 Bad Request (error code: 50035): Invalid Form Body
In embeds.0.image.url: Not a well formed URL.
```
the urls are perfectly valid? i'm not sure...


```
Traceback (most recent call last):
  File "/home/container/.local/lib/python3.8/site-packages/discord/ext/commands/core.py", line 229, in wrapped
    ret = await coro(*args, **kwargs)
  File "/home/container/cogs/Useful.py", line 204, in imgtest
    await p.start()
  File "/home/container/utils/paginator.py", line 142, in start
    self.message = await self.ctx.send(**kwargs, view=self)
  File "/home/container/.local/lib/python3.8/site-packages/discord/ext/commands/context.py", line 1016, in send
    return await super().send(
  File "/home/container/.local/lib/python3.8/site-packages/discord/abc.py", line 1561, in send
    data = await state.http.send_message(channel.id, params=params)
  File "/home/container/.local/lib/python3.8/site-packages/discord/http.py", line 744, in request
    raise HTTPException(response, data)
discord.errors.HTTPException: 400 Bad Request (error code: 50035): Invalid Form Body
In embeds.0.image.url: Not a well formed URL.
The above exception was the direct cause of the following exception:
Traceback (most recent call last):
  File "/home/container/.local/lib/python3.8/site-packages/discord/client.py", line 441, in _run_event
    await coro(*args, **kwargs)
  File "/home/container/cogs/Events.py", line 294, in on_command_error
    raise(error)
  File "/home/container/.local/lib/python3.8/site-packages/discord/ext/commands/bot.py", line 1350, in invoke
    await ctx.command.invoke(ctx)
  File "/home/container/.local/lib/python3.8/site-packages/discord/ext/commands/core.py", line 1023, in invoke
    await injected(*ctx.args, **ctx.kwargs)  # type: ignore
  File "/home/container/.local/lib/python3.8/site-packages/discord/ext/commands/core.py", line 238, in wrapped
    raise CommandInvokeError(exc) from exc
discord.ext.commands.errors.CommandInvokeError: Command raised an exception: HTTPException: 400 Bad Request (error code: 50035): Invalid Form Body
In embeds.0.image.url: Not a well formed URL.
```

https://pastebin.com/v7KERekZ

https://mystb.in/FioricetResistanceAmend

