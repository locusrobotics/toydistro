#!/usr/bin/env groovy
versions = [
  tailor_meta: "prune-environment",
  tailor_distro: "prune-environment",
  tailor_image: "prune-environment",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
