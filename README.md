# Education
Hyperledger education and training material

1. Try to run the demo in the following directory: `LFS171x/indy-material/nodejs/`
2. With the following command: `./manage build`
3. But got the following error message: 
```
failed to solve: process "/bin/sh -c pip install --no-cache-dir aiosqlite~=0.6.0"
did not complete successfully: exit code: 1
```
5. The issue was about installing the `aiosqlite` due to missing setuptools package. 
6. So I made the update in the following dockerfile, by adding `setuptools` to the pip install: `pool.dockerfile`.
```
RUN pip install --no-cache-dir setuptools~=38.6.0 && \ 
    pip install --no-cache-dir aiosqlite~=0.6.0
```
8. It worked fine, updated Dockerfile was added: `(UPDATED)pool.dockerfile`
9. When I changed the PC/Laptop, same project didn't run, I kept getting the following error:
```
Bash script and /bin/bash^M: bad interpreter: No such file or directory
```
10. Then found out that, error message was related to `Git bash` Terminal. Git bash simply did autoconfiguration while running the code, so I made configuration change in Git bash terminal:
```
#Git bash Terminal
$git config --global core.autocrlf input
```
11. Then removed the project folder: `education-Indy`
12. Cloned again: `git clone <education-Indy>`
13. Everything is fine :)
---------------------
`IMPORTANT` -> following commands are used to clean cache of `Docker`, it's used whenever try to run the image or container from the beginning, and it ends up with the some kind of issue or error    message, it's because of docker cache still keeps the previous copy of the image and container. In this case, best way is to clean the docker cache and restart the image and container.
```
$docker system prune
$docker system prune -a
$docker build prune
```
---------------------
