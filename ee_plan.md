## Channels

Name		Short name		Status Group	Field group		Category Group

Work		works			default			work			work
Blog 		blogs			default			blog			blog


## Statuses

### Default group

Open		open
Closed		closed


## Categories

### Works

- Web
- 2D
- 3D

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
	- Text file (128)
	- Mandatory
- cf_work_summary
	- Wysiwyg
	- Mandatory
- cf_work_url
	- Text file (128)
	- Mandatory


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
	- relationships


## Upload locations

- Works Images (assets/uploads/works_images)
- Blogs Images (assets/uploads/blogs_images)


## Template groups / templates

- site
	- index (homepage: intro / 3 latest works / 3 latest blog posts)
	- 404
	- page (used for about page)
- work
	- index (list)
	- detail
- blog
	- index (list)
	- post (detail)
	- rss (feed: last 10 blogposts)
- embeds
	- .page_header


## Snippets

- sn_page_footer


## Global Variables

- gv_home_title (homepage title)
- gv_home_intro (homepage intro)
- gv_work_title (work list page title)
- gv_work_intro (work list page intro)
- gv_blog_title (blog list page title)
- gv_blog_intro (blog list page intro)