#!/usr/bin/env groovy
versions = [
  tailor_meta: "build-custom-images-19.4",
  tailor_distro: "fix_19.4",
  tailor_image: "build-custom-images-19.4",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
