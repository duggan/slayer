slayer
======

Manage ArchiveTeam Warrior spot instances.

Interactively check the output of your warrior instances and terminate if
they're not doing anything.

## Requirements

`ansible` and `boto` are required for slayer to run.
These can both be installed with `pip`, see `install.sh`.

## Setup

You will need your AWS access key and secret key in the environment, or
supplied on the command line.

You can get these by visiting the "security credentials" section of the menu
in your AWS console.

In the environment:
```
export AWS_ACCESS_KEY_ID=<your access key>
export AWS_SECRET_ACCESS_KEY=<your secret key>

```

You can also set these on the command line:
```
./slayer --key=<your access key> --secret=<your secret key> --region=us-east-1
```

## Running slayer

It's pretty simple:

```
./slayer --region=us-east-1
```

If everything's set up, this will start the interactive prompt, which will
look something like this:

![4Vw46w.png](http://omg.wthax.org/4Vw46w.png)

You'll be prompted before each major action; you can either type y or n -
hitting return/enter is the same as typing n.
