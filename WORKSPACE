workspace(name = "com_github_johnynek_bazel_deps")

git_repository(
    name = "io_bazel_rules_scala",
    remote = "git://github.com/bazelbuild/rules_scala",
    commit = "388a2585f45dff804d006b0e81e1b1a1c60578bc" # update this as needed
)
load("@io_bazel_rules_scala//scala:scala.bzl", "scala_repositories")
scala_repositories()

load("//3rdparty:workspace.bzl", "maven_dependencies")
load("//tools/bazel_defs:workspace.bzl", "declare_maven")

maven_dependencies(declare_maven)

new_git_repository(
    name = "org_typelevel_paiges",
    remote = "git://github.com/typelevel/paiges",
    commit = "0cdb92ac7f40cb251a76077cb0ac92b68a620c57",
    # inconsistency in how we refer to build paths in new_native/new git
    build_file = "3rdparty/manual/BUILD.paiges",
    # use target: "@org_typelevel_paiges//:paiges"
)

new_git_repository(
    name = "com_monovore_decline",
    remote = "git://github.com/bkirwi/decline",
    # this is 0.2.2
    commit = "b3dd1442923949f1fd2822b266f2e3626919f2c6",
    # inconsistency in how we refer to build paths in new_native/new git
    build_file = "3rdparty/manual/BUILD.decline",
    # use target: "@org_typelevel_paiges//:decline"
)

bind(name = 'io_bazel_rules_scala/dependency/scalatest/scalatest', actual = '//3rdparty/jvm/org/scalatest')
