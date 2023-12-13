load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

#################################################################
# rules_dotnet - snippet from https://github.com/bazelbuild/rules_dotnet/releases
#################################################################

http_archive(
    name = "rules_dotnet",
    sha256 = "718cb2c3431523aaf3df7feed0e997e4ded002abbf56ac37d9c0536a812d6276",
    strip_prefix = "rules_dotnet-0.12.0",
    url = "https://github.com/bazelbuild/rules_dotnet/releases/download/v0.12.0/rules_dotnet-v0.12.0.tar.gz",
)

load(
    "@rules_dotnet//dotnet:repositories.bzl",
    "dotnet_register_toolchains",
    "rules_dotnet_dependencies",
)

rules_dotnet_dependencies()

# Here you can specify the version of the .NET SDK to use.
dotnet_register_toolchains("dotnet", "7.0.101")

load("@rules_dotnet//dotnet:rules_dotnet_nuget_packages.bzl", "rules_dotnet_nuget_packages")

rules_dotnet_nuget_packages()

# Support paket dependency manager which simplifies use of nuget
load("@rules_dotnet//dotnet:paket2bazel_dependencies.bzl", "paket2bazel_dependencies")
paket2bazel_dependencies()

load("@//deps:paket.bzl", "paket")
paket()
