# forked

run

```

pip install thomasthechatbot

```
then type
```
ttc
```
in the command line.

# first interaction
## tip open new issue on github, paste image, get URL, paste!
![image](https://user-images.githubusercontent.com/640846/201272702-ad6bc058-6569-407a-b71d-a91d99a14227.png)

The chatbot is not super smart. Not clear on how to train the brain(s) either.

# original README below

# Installation

**Python 3.9+ is required**

This package can be installed from [PyPi](https://pypi.org/project/thomasthechatbot/) with:

```

pip install thomasthechatbot

```

## CLI

Type `ttc` to begin talking to Thomas.

# How does Thomas work?

I wrote a [medium article](https://medium.com/@principle105/creating-a-python-chatbot-that-learns-as-you-speak-to-it-60b305d8f68f) to explain how Thomas works.

# Usage

## Basic Usage

```py
from ttc import Chatbot, Context, download_nltk_data

# Only needs to be run once (can be removed after first run)
download_nltk_data()

# Creating the context
ctx = Context()

# Initializing the chatbot
chatbot = Chatbot()

talk = True

while talk:
    msg = input("You: ")

    if msg == "s":
        talk = False
    else:
        # Getting the response
        resp = chatbot.respond(ctx, msg)

        # Saving the response to the context
        ctx.save_resp(resp)

        print(f"Thomas: {resp}")

# Saving the chatbot data
chatbot.save_data()
```

## Configurations

```py
chatbot = Chatbot(
    path="brain",
    learn=False,
    min_score=0.5,
    score_threshold=0.5,
    mesh_association=0.5,
)
```

# Contributing

Open to contributions, please create an issue if you want to do so.

# Formatting

[Black](https://github.com/psf/black), [isort](https://github.com/PyCQA/isort) and [Prettier](https://prettier.io/) are used for formatting
