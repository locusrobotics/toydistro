#!/usr/bin/env groovy
versions = [
  tailor_meta: "master",
  tailor_distro: "master",
  tailor_image: "RST-1786_Add-bare-metal-image-creation-CI_with-dev-hotdog",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
