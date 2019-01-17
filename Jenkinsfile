#!/usr/bin/env groovy
versions = [
  tailor_meta: "release-track",
  tailor_distro: "master",
  tailor_image: "release-track",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
