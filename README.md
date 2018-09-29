Gitbook Container
=========

Containerizes the `gitbook-cli` and installs the gitbook server application. The directory `/var/books` is created as a mount point for books volume.

Running Gitbook Container
```
docker run -it \
--rm \
--name gitbook \
--volume "$(pwd)/test-book":/var/books \
--publish 4000:4000 \
brockresearch/gitbook /bin/sh
```

Once you launch the container you can create minimal book skeletons within the `/var/books` directory from within the container using the command `gitbook init /var/books/<bookname here>`. The will create a `README.md` and a `SUMMARY.md` which for the bare-minimum content for a gitbook. When the book skeleton in place change into the books directory and execute `gitbook serve .` The `serve` option of the `gitbook` command launches a NodeJS based web page that serves up the book's content.

**NOTE:** You may have to run the `gitbook serve` more that once before it recognizes the `_book/gitbook/gitbook-plugin-sharing/buttons.js` file does infact exists. There is a defect open since in 2016 regarding this issue.