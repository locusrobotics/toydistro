#!/usr/bin/env groovy
versions = [
  tailor_meta: "RST-1658_Update-repo-settings-on-build",
  tailor_distro: "master",
  tailor_image: "master",
]

library('tailor-meta@' + versions['tailor_meta'])_
tailorDistroPipeline(
  versions: versions
)
