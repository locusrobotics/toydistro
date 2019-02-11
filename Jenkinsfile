#!/usr/bin/env groovy
versions = [
  tailor_meta: "test-rosdep",
  tailor_distro: "master",
  tailor_image: "test-rosdep",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
