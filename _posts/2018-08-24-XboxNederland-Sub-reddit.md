---
layout: post
title: XboxNederland subreddit
source: 
---
dit is een test om te kijken hoe dit werkt
<!--break-->

If you want to start editing the new commit message with a concatenation of the existing commit messages, then you need to extract those messages and pass them to git commit:

{% highlight sh %}
$ git reset --soft HEAD~3 &&
$ git commit --edit -m"$(git log --format=%B --reverse HEAD..HEAD@{1})"
{% endhighlight %}

Both of those methods squash the last three commits into a single new commit in the same way. The soft reset just re-points HEAD to the last commit that you do not want to squash. Neither the index nor the working tree are touched by the soft reset, leaving the index in the desired state for your new commit (i.e. it already has all the changes from the commits that you are about to “throw away”).
