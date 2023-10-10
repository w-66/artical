# \[En]docker pull 官方文档

<https://docs.docker.com/engine/reference/commandline/pull/>

## Description

Pull an image or a [repository](repository_91JBNa7hbaUQ2WQFqyL3zd.md "repository") from a [registry](registry_daH6yhyhLgzd2F7FJKSWc3.md "registry")
从注册表中拉取或者存储

## Usage

```纯文本
docker pull [OPTIONS] NAME[:TAG|@DIGEST]
```

## Extended description

Most of your images will be created on top of a base image from the [Docker Hub](https://hub.docker.com "Docker Hub") registry.
您的大部分基础镜像都将在来自 Docker Hub 注册表的基本镜像之上创建。

[Docker Hub](https://hub.docker.com "Docker Hub") contains many pre-built images that you can `pull` and try without needing to [define](define_izeJmW4azjwuiSFX88FXUx.md "define") and [configure](configure_wyo96UXrwr261aaRoU8WNG.md "configure") your own.
Docker Hub 包含许多预构建的镜像，您可以拉取和尝试这些镜像，而无需定义和配置您自己的镜像。

To download a [particular](particular_x2XsHbmq4Wg83wJCYoLied.md "particular") image, or set of images (i.e., a [repository](repository_91JBNa7hbaUQ2WQFqyL3zd.md "repository")), use `docker pull`.
下载特定的镜像或者一组镜像（即存储库），使用`docker pull`

### Proxy configuration

If you are [behind](behind_tyBbc32eQ6TERa5Sa9WmGZ.md "behind") an HTTP proxy server, for example in corporate settings, before open a connect to registry, you may need to configure the Docker daemon’s proxy settings, using the `HTTP_PROXY`, `HTTPS_PROXY`, and `NO_PROXY` environment variables. To set these environment variables on a host using `systemd`, refer to the [control and configure Docker with systemd](https://docs.docker.com/config/daemon/systemd/#httphttps-proxy "control and configure Docker with systemd") for [variables](variables_khYq4jAU15W5cQLnt3N8tY.md "variables")  [configuration](configuration_q3YCrTAcZhgmvQ5GhbYSYy.md "configuration").

### Concurrent downloads

by default the Docker daemon will pull [three](three_5bQvSD1ygG2qk3rkXVDWcz.md "three") layers of an image at a time. If you are on a low bandwidth connection this may [cause](cause_kXaTK5nLL6zdsRL1nwLsU2.md "cause")  timeout issues and you may want to lower this [via](via_pfxSsm1HiJ6FFqhYBCBcMp.md "via") the `--max-concurrent-downloads` daemon option. See the [daemon documentation](https://docs.docker.com/engine/reference/commandline/dockerd/ "daemon documentation") for more details.

## Options

| Name, shorthand           | Default | Description                                                                                                        |
| ------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------ |
| `--all-tags` ,`-a`        |         | Download all tagged images in the repository                                                                       |
| `--disable-content-trust` | `true`  | Skip image verification                                                                                            |
| `--platform`              |         | [API 1.32+](https://docs.docker.com/engine/api/v1.32/ "API 1.32+")Set platform if server is multi-platform capable |
| `--quiet` , `-q`          |         | Suppress verbose output                                                                                            |

## Examples

### Pull an image from Docker Hub

To download a [particular](particular_x2XsHbmq4Wg83wJCYoLied.md "particular") image, or set of images (i.e., a repository), use `docker pull`. If no tag is provided, Docker Engine uses the `:latest` tag as a default. This command pulls the `debian:latest` image:

```yaml
$ docker pull debian

Using default tag: latest
latest: Pulling from library/debian
fdd5d7827f33: Pull complete
a3ed95caeb02: Pull complete
Digest: sha256:e7d38b3517548a1c71e41bffe9c8ae6d6d29546ce46bf62159837aad072c90aa
Status: Downloaded newer image for debian:latest
```

Docker images can [consist](consist_i42yAB9aZ4AxeXUoY2NUJs.md "consist") of multiple layers. In the example [above](above_rb7VsfG8sa28SGzMxfRd8D.md "above"), the image consists of two layers; `fdd5d7827f33` and `a3ed95caeb02`.

Layers can be reused by images. for [example](example_8ox5rjU8vHXKoXuL7jwmNK.md "example"), the `debian:jessie` image shares both layers with `debian:latest`. Pulling the `debian:jessie` image [therefore](therefore_fQjPLY4U7z7wVeQ9L3U38k.md "therefore") only pulls [its](its_g7oymhUAEEY2CXjmcDDQyn.md "its") metadata, but not its layers, because all layers are already [present](present_uHZjbeEDN166JWapqArbKv.md "present") [locally](locally_6s8QbxA8jtUoSAdXwLpiBx.md "locally"):

```纯文本
$ docker pull debian:jessie

jessie: Pulling from library/debian
fdd5d7827f33: Already exists
a3ed95caeb02: Already exists
Digest: sha256:a9c958be96d7d40df920e7041608f2f017af81800ca5ad23e327bc402626b58e
Status: Downloaded newer image for debian:jessie
```

To see which images are present locally, use the [docker images](https://docs.docker.com/engine/reference/commandline/images/ "docker images") command:

Docker uses a [content](content_qbf4hoiuMJ8X6ZLrbrjCT6.md "content") [addressable](addressable_rcTgKqZQmeV4uzsitQ2DNj.md "addressable") image store, and the image ID is a SHA256 [digest](digest_d5fJb2XrrVmgNByubUa24y.md "digest") covering the image's configuration and layers. In the example above, `debian:jessie` and `debian:latest` have the same image ID because they are [actually](actually_7jiF9uztSSdgtjSbmgdJXW.md "actually") the *same* image tagged with different names. Because they are the same image, their layers are stored only once and do not [consume](consume_3KBwYEiiRJeUkqjNveFJLR.md "consume") [extra](extra_R4aU6VPBfizwdmDRgjxyx.md "extra") disk space.
Docker使用内容可寻址的图像存储，并且图像ID是涵盖图像的配置和层的SHA256摘要。在上面的示例中，debian:jessie和debian:latest具有相同的图像ID，因为它们实际上是用不同名称标记的相同图像。因为它们是相同的映像，所以它们的层仅存储一次，并且不会消耗额外的磁盘空间。

For more information about images, layers, and the content-addressable store, refer to [understand images, containers, and storage drivers](https://docs.docker.com/storage/storagedriver/ "understand images, containers, and storage drivers").

## Pull an image by [digest](digest_d5fJb2XrrVmgNByubUa24y.md "digest") ([immutable](immutable_vW1jbxduki71cCFLvSPbsf.md "immutable") [identifier](identifier_kNUcsX4SC8J7gkbyjD7f9F.md "identifier"))

so far，[you've](you've_9ZhZPozu9anK9QEr2cpWVw.md "you've") pulled images by their name (and “tag”). Using names and tags is a [convenient](convenient_dgWvm7NkH6XnMDgBj9KshH.md "convenient") way to work with images. When using tags, you can `docker pull` an image again to [make](make_wfWqS66sZiR6ao5Bi9JPw8.md "make") [sure](sure_vPpLsr5eZZLdRTdYiHe6Xa.md "sure") you have the most up-to-date version of that image. For example, `docker pull ubuntu:14.04` pulls the latest version of the Ubuntu 14.04 image.

in some cases  you don't want images to be updated to newer versions, but [prefer](prefer_mmxUPcWib2hXt7M68R22uB.md "prefer") to use a fixed version of an image. Docker enables you to pull an image by its [digest](digest_d5fJb2XrrVmgNByubUa24y.md "digest"). When pulling an image by digest, you specify *exactly* which version of an image of an image to pull. Doing so, allows you to “[pin](pin_foVYxzEudctYbLmhzYM5af.md "pin")” an image to that version, and [guarantee](guarantee_xt87ReD1qWo9xN4YEXZtJa.md "guarantee") that the image you're using is always the [same](same_5s22L3x88zuHZteRoW2jHc.md "same").

To know the digest of an image, pull the image first. Let’s pull the latest `ubuntu:14.04` image from Docker Hub:

```纯文本
$ docker pull ubuntu:20.04

20.04: Pulling from library/ubuntu
16ec32c2132b: Pull complete
Digest: sha256:82becede498899ec668628e7cb0ad87b6e1c371cb8a1e597d83a47fac21d6af3
Status: Downloaded newer image for ubuntu:20.04
docker.io/library/ubuntu:20.04
```
