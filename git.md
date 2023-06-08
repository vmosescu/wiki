
```
$ git --version
$ git config --global http.sslCAinfo <cer_path_file>
$ git clone <url>
$ git status
$ git add . (add to staging)
$ got commit -m "message"

$ git restore --staged <path>
$ git restore <path> (from staging)
$ git ls-files
$ git log

$ git clone
$ git fetch
$ git ckeckout <remote>

$ git checkout develop <path> (from develop in current branch)

$ git fetch
$ git pull

$ git branch
$ git branch <name> (new branch from current branch)
$ git checkout <name>
$ git merge <name> (name -> current branch)
$ git branch -d <name> (delete)

$ git remote add origin <url>
$ git remote -v
$ git push -u origin master (only first time)
$ git push

$ git clone <url>
git add, commit, push

$ git pull -> could be conflicts

$ git branch
$ git log hotfix/EPS-3258-fix-xml-factory-3.0.0
$ git cherry-pick -n a331031e5c361bd73cf3662b15941740dda046e9

```  

## access a web server running in a container and docker is installed into a vm
 - container port 8080 is published on port 80 in docker vm
```
$ docker run -p 8080:80
```
- port forward 80 to 80 (host to vm)
- access http://localhost:80 on host
