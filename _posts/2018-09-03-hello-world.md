---
layout: post
title:  "Hello World!"
date:   2018-09-03 20:58:56 +0200
categories: jekyll test
---
Yep, I'm up and running!

```python
def do_something(name, b=2)
    """
    This is a multiline comment that
    spans multiple lines, yey!
    """
    return f"the name equals '{name}'"

if __name__ == "__main__":
    print(do_something("hello"))
```

```python
class MessageQueueService(object):

    def log(self, message, queue, host, direction=MessageQueueLog.RECEIVED):
        message_log = MessageQueueLog.objects.create(
                queue=queue,
                host=host,
                message=message,
                direction=direction
            )
        return message_log
```

```python
#!/usr/bin/python3

from engine import RunForrestRun

"""Test code for syntax highlighting!"""

class Foo:
	def __init__(self, var):
		self.var = var
		self.run()

	def run(self):
		RunForrestRun()  # run along!
```

{% include hough.html %}
