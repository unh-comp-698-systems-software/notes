# A source for frequently asked questions and debugging tips


## Questions

Q: What does the error `docker: Error response from daemon: containerd: container not started` mean?

Hint: See debugging tip 1)

## Debugging Tips

**1) Does my image have all the required files?**

At this point, your docker image should have at least the following files.

* Dockerfile
* docker-compose.test.yml
* run_tests.sh (or run_test.sh or run-test.sh whatever matches the contents of the docker-compose.test.yml file)
* unh698.py
* unh698_test.py

Continue to Hint 2)

If you are missing files in your docker image, check your github repo's master branch to ensure that they are there.

**2) How do I see what files are in my docker image?**

On your AWS server, pull your latest image from Docker cloud.

```bash
docker pull [username]/docker-cloud-test:latest
```

Then run the following to list the files that exist in the working directory of your image.

```bash
docker run [username/docker-cloud-test] ls
```
