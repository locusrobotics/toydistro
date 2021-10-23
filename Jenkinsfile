#!/usr/bin/env groovy
versions = [
  tailor_meta: "dont-build-bundle",
  tailor_distro: "0.1.18",
  tailor_image: "build-custom-images-19.7",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
