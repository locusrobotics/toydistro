#!/usr/bin/env groovy
versions = [
  tailor_meta: "master",
  tailor_distro: "master",
  tailor_image: "build-custom-images-19.7",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
