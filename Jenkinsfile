#!/usr/bin/env groovy
versions = [
  tailor_meta: "master",
  tailor_distro: "regression-test",
  tailor_image: "master",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
