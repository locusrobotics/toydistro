#!/usr/bin/env groovy
versions = [
  tailor_meta: "master",
  tailor_distro: "RST-1600_Add-invalidation-for-cloudfront",
  tailor_image: "master",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
