#!/usr/bin/env groovy
versions = [
  tailor_meta: "master",
  tailor_distro: "rosdistro-upload-fix",
  tailor_image: "master",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
