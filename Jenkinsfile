#!/usr/bin/env groovy
versions = [
  tailor_meta: "rosdistro-upload-fix",
  tailor_distro: "master",
  tailor_image: "master",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
