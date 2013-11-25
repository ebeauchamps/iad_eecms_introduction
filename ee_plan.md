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
	- textfield (256)


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
	- rss (blog)
- work
	- index (list)
	- detail
- blog
	- index (list)
	- post (detail)
- about
	- index (page module)
- embeds
	- .page_header


## Snippets

- sn_page_footer


## Global Variables

- gv_home_intro
- gv_worklist_title
- gv_worklist_intro
- gv_bloglist_title
- gv_bloglist_intro
- gv_footer_text