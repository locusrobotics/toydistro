#!/usr/bin/env groovy
versions = [
  tailor_meta: "master",
  tailor_distro: "master",
  tailor_image: "use-separate-build-bundle",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
