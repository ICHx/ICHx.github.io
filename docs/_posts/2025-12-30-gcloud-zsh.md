---
layout: post
title:  "The rabbit hole into zsh completion"
categories: blog
---
With Mac, most of us install Oh My Zsh and Homebrew for efficient terminal management. However, it is notorious for slow startup.

Recently, I switched from Oh My Zsh to Prezto; seeing my shell ready in a second is deeply satisfying.

cont:
Although prezto is much faster, there came with a cost. I would be seeing bugs omz would have normally smoothed out for us behind the scene.

This morning, just after I installed gcloud from brew, and find the completion not working, that dragged me down the rabbit hole.

Checked fpath (normal), checked manual sourcing (it's working), but the completion is still not automatically picked up. AI told me to source manually, I know it would work, but it's not elegant.

A brief search led me to this "unplanned" issue in cask, saying that because the gcloud definition doesn't comply with zsh standard to include "hashtag#compdef gcloud ..." in the header, and in brew's convention it named the completion script to be the same as the package name "google-cloud-sdk" (
`/opt/homebrew/share/zsh/site-functions/_google_cloud_sdk`) instead of gcloud (the name that should triggers in terminal completion).

Adding that header line fixed the issue right away.

the issue:
[google-cloud-sdk zsh autocompletion doesn't load automatically #143596](https://github.com/Homebrew/homebrew-cask/issues/143596)

Google Cloud Google for Developers

Originally on Linkedin.
