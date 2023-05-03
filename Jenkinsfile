#!/usr/bin/env groovy
versions = [
  tailor_meta: "master",
  tailor_distro: "master",
  tailor_image: "fix-bundler",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
