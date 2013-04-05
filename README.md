slayer
======

Manage ArchiveTeam Warrior spot instances.

Interactively check the output of your warrior instances and terminate if
they're not doing anything.

## Requirements

`ansible` and `boto` are required for slayer to run.
These can both be installed with `pip`, see `install.sh`.

## Setup

Clone this repository like so:
```
git clone git@github.com:duggan/slayer.git
cd slayer
```

or [download a zip](https://github.com/duggan/slayer/archive/master.zip).

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

You'll also need to make your SSH key for the instances available with `ssh-agent`:

```
ssh-agent
ssh-add ~/your-key.pem
ssh-add ~/your-other-key.pem
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

Other options:

```
usage: slayer [-h] [-k KEY] [-s SECRET] -r REGION [-l LINES]

Manage your warrior cluster.

optional arguments:
  -h, --help            show this help message and exit
  -k KEY, --key KEY     AWS key.
  -s SECRET, --secret SECRET
                        AWS secret.
  -r REGION, --region REGION
                        The AWS region to operate in.
  -l LINES, --lines LINES
                        Number of lines of console output to show from each
                        warrior.
```
