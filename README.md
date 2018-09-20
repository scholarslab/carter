# Carter project archive
Static generated files from http://carter.lib.virginia.edu

## Process of creating the static archive
- Scraping the old site was done with this command:
  - `wget --mirror -P static-content -nH -np -p -k -E http://carter.lib.virginia.edu/`
- All files were archived in a bzip2.tar file using this command:
  - `tar -jcf carter.bzip2.tar releases/20160718212523`
- There was an old GitHub repo under waynegraham's account, but it no longer exists
- To recreate the site, use Docker to build an nginx container with the folder 'static-content' linked to the folder /usr/share/nginx/html in the container.
  - The docker-compose file needs to have the static-content folder and an nginx default.conf file available.

## For Production
- Copy contents of 'static-content' to the project directory on the server.
