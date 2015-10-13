---
layout: post 
title: How I Made This Website
---

I always wanted to make my own website; it's like a personal statement on the internet and if there was an archive of all the attempts I have made to make a website then I suspect that archive would be quite full. Now, for the first time, I have created (read forked) something which I like - to a certain extent. My [original website](http://jeel-shah.github.io) was designed by me whereas this one, was ddesigned by [@mdo](http://twitter.com/mdo), one of the creators of [Bootstrap](http://getbootstrap.com). My goal, for the future, is to make some more changes to the website include some subtle design changes and adding some functiosn like a button on the bottom every post which allows the reader to convert that post to `.pdf` or share it etc but that will come later. 

Today, I want to show you how to make your very own github pages site. The first thing to notice is that this is a project site which means that it uses the `gh-pages` branch on a repo called "my-notes".That is important. 

#### Things You Will Need
1. A GitHub account
2. Some patience
3. and ....

... honestly, this might possibly be the easiest thing you have ever done - ever.

## Let's Get Started 

The first think you need to do is head on over to either [my repo](http://github.com/jeel-shah/my-notes) or the [original repo](https://github.com/poole/lanyon) and fork it. 

![what to fork](http://i61.tinypic.com/fx78xw.jpg)

This will be your starting point. If you don't like the theme, you change that later or you can find another repo that you do like and fork that one; for the most part the process should be the same. Once you have forked the repo, head over to setting on the right side and change the repo name to `username.github.io` where `username` is your username. Once those changes have taken place, your site should be live at `username.github.io`. BAM! Done. It may take a few minutes - remember the second thing in our list of things we will need. There some changes which need to be done in `_config.yml` file but I will get to those in a minute.

### Setting up a project page

If you are already have a website at `username.github.io` then you will have to make a project page which is almost as easy. Head over to the settings of your recently forked repo and name the repo whatever you want.

![name change](http://i61.tinypic.com/30jp3so.jpg). 

Then the site will be live at `username.github.io\project-name`. That wasn't so hard now was it?

### Changes to _config.yml File

There are some changes which you will need to make to the `_config.yml` file depending on whether this _your website_ or _your project page_. If it is _your website_ then simply go to your `_config.yml` file and make changes to the `author`, `description` etc. However, if this a project page _and you did fork my repo_ then you will have to make a change to the `baseurl`. The `baseurl` will make urls which will point to `username.github.io\project-name` rather than `username.github.io`. Make sure to change your baseurl to the name of your repo with **no** trailing \'s. 

![config settings](http://i59.tinypic.com/2vv6fra.jpg)

Once you have done that, you are good to go because I have made the other changes. These changes being going into the the `_layout` files and adding `{{ site.baseurl }}` to `<a>` tags. That being said, if you did not fork my repo and forked the orignal one or another one that you liked then go through the following steps. 

1. Add `siteurl: \project-name` to your `_config.yml` file, anywhere will do (unindented). 
2. Find where your css/js is being referenced and change the path to something like `{{ site.baseurl}}/path/to/css`. Do this for all of your css/js
3. Go to `_layouts` folder and access each file to replace `<a>` tags like `<a href="{{ post.url }}">` to `<a href="{{ site.baseurl }}{{ post.url }}">`
4. Celebrate

If you are using a repo that is neither mine or the original then you will have to track down the `<a> tags` and fashion them like the above **if** `_config.yml` does not contain `baseurl` and all the paths are done in an absolute fashion.

And that's it.

### Conclusion

I haven't mentioned how to run this locally because I don't think it necessary if you aren't overhauling the design. There are a number of tutorials which teach you have to run jekyll locally. If you anyquestions feel free to shoot me a [tweet](http://twitter.com/jeel-shah). 
