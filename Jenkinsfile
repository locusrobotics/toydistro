#!/usr/bin/env groovy
versions = [
  tailor_meta: "master",
  tailor_distro: "fix-bundler",
  tailor_image: "master",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
