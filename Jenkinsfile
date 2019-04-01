#!/usr/bin/env groovy
versions = [
  tailor_meta: "master",
  tailor_distro: "test-image-creation",
  tailor_image: "RST-1750_Use-packer-ansble-to-build-test-dev-images",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
