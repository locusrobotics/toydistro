#!/usr/bin/env groovy
versions = [
  tailor_upstream: "master",
  tailor_distro: "master",
  tailor_image: "master",
  tailor_meta: "master",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
