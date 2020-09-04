---
description: How to download (clone) the NuttX source code using Git.
---

# Download NuttX

## Repositories

NuttX consists of two repositories. The main operating system and an additional set of applications. Both repositories need to be in the same parent folder, with the main operating system being in a folder named "nuttx" and the applications have to be in a folder named "apps".

* **NuttX -** [https://github.com/apache/incubator-nuttx](https://github.com/apache/incubator-nuttx)
* **Apps -** [https://github.com/apache/incubator-nuttx-apps](https://github.com/apache/incubator-nuttx-apps)

Let's start by creating a parent folder to store both repositories. The following command will create an "apache-nuttx" folder if it doesn't exist already and makes it the active working directory.

```bash
mkdir -p ~/src/apache-nuttx && cd ~/src/apache-nuttx
```

We can now clone the Git repository that contains the main operating system. We'll immediately name the folder "nuttx" because the build system might get lost if it has a different name.

```bash
git clone https://github.com/apache/incubator-nuttx.git nuttx
```

Similarly, we'll clone the apps repository:

```bash
git clone https://github.com/apache/incubator-nuttx-apps.git apps
```

You should now have a "apache-nuttx" folder located at `~/src/` that contains two folders: "nuttx" and "apps". That's all you need.

## Checkout a stable release

By default Git will checkout the latest commit in the master branch when you clone the repositories. This is the latest development version at that point in time. Keep in mind that if you want to keep up with any changes you should use `git pull` to pull in any new commits. Keep in mind to do this for both the "nuttx" and the "apps" repositories.

You can also checkout the latest stable release. Change your working directory to the first repository, and fetch the available tags.

```bash
git fetch && git fetch --tags
```

Now that the tags are available locally, you can checkout a particular release. At the time of writing the latest stable release is NuttX 9.1.0. You can checkout this particular version with the following command:

```bash
git checkout nuttx-9.1.0
```

Don't forget to do both steps for both repositories! A particular version of the NuttX OS always should be matched by the same version of the NuttX Apps.

