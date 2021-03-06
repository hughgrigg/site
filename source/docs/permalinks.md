title: Permalinks
---
You can specify the permalinks for your site in `_config.yml` or in the front-matter for each post.

### Variables

Besides the following variables, you can use any attributes in the permalink since Hexo 2.5.

Variable | Description
--- | ---
`:year` | Published year of posts (4-digit)
`:month` | Published month of posts (2-digit)
`:i_month` | Published month of posts (Without leading zeros)
`:day` | Published day of posts (2-digit)
`:i_day` | Published day of posts (Without leading zeros)
`:title` | Filename
`:id` | Post ID
`:category` | Categories. If the post is uncategorized, it'll be `category_dir` setting.

You can define the default value of each variable in the permalink in `permalink_defaults` setting:

``` yaml
permalink_defaults:
  lang: en
```

### Examples

Given a post named `hello-world.md` in `source/_posts` folder with the following content.

``` yaml
title: Hello World
date: 2013-07-14 17:01:34
categories:
- foo
- bar
```

Setting | Result
--- | ---
`:year/:month/:day/:title/` | 2013/07/14/hello-world
`:year-:month-:day-:title.html` | 2013-07-14-hello-world.html
`:category/:title` | foo/bar/hello-world

### Multi-language Support

To create a multi-language site, you can modify `new_post_name` and `permalink` setting like this:

``` yaml
new_post_name: :lang/:title.md
permalink: :lang/:title/
```

When you create a new post, the post will be saved to:

``` bash
$ hexo new "Hello World" --lang tw
# => source/_posts/tw/Hello-World.md
```

and the URL will be:

``` plain
http://localhost:4000/tw/hello-world/
```