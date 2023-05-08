build:
	hugo
clean:
	rm -r dist/
post:
	echo "---" > content/posts/$(POST_NAME).md;
	echo "title: $(POST_TITLE)" >> content/posts/$(POST_NAME).md;
	echo "draft: true" >> content/posts/$(POST_NAME).md;
	echo "---" >> content/posts/$(POST_NAME).md;
