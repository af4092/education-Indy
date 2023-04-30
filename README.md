# Education
Hyperledger education and training material

1. Try to run the demo in the following directory: `LFS171x/indy-material/nodejs/`
2. With the following command: `./manage build`
3. But got the following error message: `failed to solve: process "/bin/sh -c pip install --no-cache-dir aiosqlite~=0.6.0" did not complete successfully: exit code: 1`
4. The issue was about installing the `aiosqlite` due to missing setuptools package. 
5. So I made the update in the following dockerfile, by adding `setuptools` to the pip install: `pool.dockerfile'. 
6. It worked fine.
