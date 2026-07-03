---
layout: post
title:  letting root use homebrew installed packages
categories: blog
---
By default your homebrew installed tools aren't available in other user, requiring us to do like `sudo $(which xyz)`.
```sh
> sudo crictl ps
sudo: crictl: command not found
```
This guide aims to remedy that.

## Procedures
1. Add shellenv to your root zshrc/bashrc
	```sh
    # Add one of the following line
	Apple Silicon: eval "$(/opt/homebrew/bin/brew shellenv)"
	Intel Mac: eval "$(/usr/local/bin/brew shellenv)"
	Linux: eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
	```
2. Edit sudoer with visudo
	```sh
	# Change visudo secure_path
	Apple Silicon Macs: Add :/opt/homebrew/bin
	Linux: Add :/home/linuxbrew/.linuxbrew/bin
	```
3. Viola, tools should be available in root shell/sudo as well.
