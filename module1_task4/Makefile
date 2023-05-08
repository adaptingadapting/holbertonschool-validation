build: ## builds the website with go hugo
	hugo

clean: ## cleans the destination directory of the publication
	rm -r dist/

post: ## posts a new article to post name titled post title
	echo "---" > content/posts/$(POST_NAME).md;
	echo "title: $(POST_TITLE)" >> content/posts/$(POST_NAME).md;
	echo "draft: true" >> content/posts/$(POST_NAME).md;
	echo "---" >> content/posts/$(POST_NAME).md;

help: ## displays the commands comments
	grep "##" Makefile | head -n -1 | cut -d "#" -f 3 | cut -b 2-

