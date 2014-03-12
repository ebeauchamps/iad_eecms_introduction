## Channels

- Work
	- short name: works
	- status group: default
	- field group: work
	- category group: none
- Blog
	- short name: blogs
	- status group: default
	- field group: blog
	- category group: blog

## Statuses

### Default group

- Open | open
- Closed | closed


## Categories

### Blogs

- Geeky stuff
- Life
- Work


## Custom Fields

### Works

- title
- url_title
- date
- cf_work_img
	- File field (assets/uploads/work_img)
	- Mandatory
- cf_work_imgcaption
	- Text field (128)
	- Mandatory
- cf_work_url
	- Text field (128)
	- Mandatory
- cf_work_summary
	- Wysiwyg
	- Mandatory
- cf_work_body
	- Text field (256)
	- Mandatory
- cf_work_gallery
	- Grid (gd_screenshot, gd_caption)


### Blogs

- title
- url_title
- date
- cf_blog_summary
	- Wysiwyg
	- Mandatory
- cf_blog_body
	- Wysiwyg
	- Mandatory
- cf_blog_related
	- relationships (blogs, open)


## Upload locations

- Works Images (assets/uploads/works_images)
- Blogs Images (assets/uploads/blogs_images)


## Template groups / templates

Using the template / layout inheritance available in 2.8

- site
	- index (homepage: title / intro / 3 latest works / 3 latest blog posts)
	- 404
	- page (used for about page)
- work
	- index
	- detail
- blog
	- index
	- post
	- rss (feed: last 10 blogposts)
- layouts
	- _page


## Global Variables

- gv_home_title (homepage title)
- gv_home_intro (homepage intro)
- gv_worklist_title (work list page title)
- gv_worklist_intro (work list page intro)
- gv_bloglist_title (blog list page title)
- gv_bloglist_intro (blog list page intro)