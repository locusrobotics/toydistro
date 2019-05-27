#!/usr/bin/env groovy
versions = [
  tailor_meta: "master",
  tailor_distro: "test-image-creation",
  tailor_image: "test-packer-1-4-1",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
