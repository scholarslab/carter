# Carter project archive
Static generated files from http://carter.lib.virginia.edu

## Process of creating the static archive
- Scraping the old site was done with this command:
  - `wget --mirror -P static-content -nH -np -p -k -E http://carter.lib.virginia.edu/`
- All files were archived in a bzip2.tar file using this command:
  - `tar -jcf carter.bzip2.tar releases/20160718212523`
- There was an old GitHub repo under waynegraham's account, but it no longer exists
- To recreate the site
  - Put the contents of the 'static-content' folder on a web server. It is just static HTML files.
  - Or use Docker to build an nginx container with the folder 'static-content' linked to the folder /usr/share/nginx/html in the container.
    - The docker-compose.yml file needs to have the static-content folder on the same level as itself.
    - The docker-compose.yml file requires Traefik to be running and a 'thenetwork' docker network to be created. See here: https://github.com/scholarslab/traefik


## File Structure

```
├── README.md
├── carter.bzip2.tar
├── docker-compose.yml
└── static-content
```
